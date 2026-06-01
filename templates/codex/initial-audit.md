# Codex Template: Initial Audit

Copy the prompt below into Codex when starting work on an unknown or newly cloned app repository.

```md
# Initial Audit Prompt

## Purpose

Audit this repository before implementation so we understand its structure, run commands, configuration, risks, and safest next actions.

## When to use

Use this when:

- Starting work in a new repository
- Returning to a project after a long gap
- Preparing to split work into iOS, backend, release, or bugfix threads
- Checking whether the project is safe to build, test, or modify

## Inputs

Project context:
- App/product name:
- Target platforms: [iOS / backend / web / combined / unknown]
- Known stack: [SwiftUI / FastAPI / other / unknown]
- Intended task after audit:
- Environment available locally:
- Anything that must not be touched:

## Constraints

- Treat the current repository as the source of truth.
- Inspect before recommending changes.
- Do not edit application code during the audit unless explicitly asked.
- Prefer local, read-only inspection commands first.
- If a command may contact external services, modify data, or require credentials, stop and ask first.
- Keep findings specific to files, commands, settings, and risks found in this repository.

## Safety rules

Do not perform these without explicit human confirmation:

- Production database writes or migrations
- External API sends, emails, notifications, or webhooks
- GitHub push, git tag, or GitHub release creation
- Release creation, deployment, or package publishing
- App Store submission or TestFlight submission
- Billing, subscription, IAP, signing, or provisioning changes
- Destructive file, infrastructure, or data operations

If a side-effect operation is needed, stop before running it and present:

- target command / endpoint / screen
- payload or operation details
- impact scope
- rollback plan

## Required checks

Inspect and report on:

- Repository structure: main directories, app targets, backend services, scripts, docs
- Build method: Xcode, Swift Package Manager, Makefile, npm, Python, Docker, FastAPI, or other
- Test method: unit tests, UI tests, backend tests, lint, format, type checks
- Environment setup: `.env` examples, config files, required variables, local setup docs
- Secret handling: committed secrets risk, placeholder usage, ignored files
- Localhost usage: hardcoded `localhost`, `127.0.0.1`, simulator/device networking assumptions
- API connections: base URLs, clients, generated API code, external service dependencies
- Database and migrations: migration tooling, local vs production config, dry-run support
- Release signals: version/build files, release notes, App Store/TestFlight/backend deploy files
- Existing progress tracking: TODOs, issue references, roadmap, checklists

Use commands such as file listing, text search, and safe local metadata inspection. Do not run builds, tests, migrations, package installs, or networked commands until you have identified what they do.

## Work order

1. Inspect file and directory structure.
2. Identify stack, app entry points, backend entry points, and release-related files.
3. Identify how to run, build, test, lint, and verify locally.
4. Identify required environment variables and secret risks.
5. Identify API, localhost, and database/migration risks.
6. Classify findings into P0, P1, and P2.
7. Recommend the next concrete action and the best follow-up thread type.

P0 means blocking or unsafe before development continues.
P1 means important for practical development but not immediately blocking.
P2 means useful cleanup or later improvement.

## Output format

Return exactly these sections:

## Repository Summary

## Structure Map

## Stack And Entry Points

## Local Build / Run / Test Commands

For each command include:
- command
- purpose
- whether it is safe to run now
- reason if not safe

## Environment And Secrets

## Localhost / API / Database / Migration Notes

## Release And Distribution Signals

## Risk Classification

### P0

### P1

### P2

## Recommended Next Action

## Suggested Next Thread

## Human Confirmation Needed

For each item include:
- target command / endpoint / screen
- payload or operation details
- impact scope
- rollback plan

## Done criteria

The audit is done only when:

- The repository structure has been summarized.
- Build, run, test, and verification paths are identified or explicitly marked unknown.
- Environment, localhost, API, secret, and migration risks are checked.
- P0/P1/P2 risks are classified.
- The next action is specific enough for another Codex thread to start.
- Any side-effect operation is listed but not executed.
```
