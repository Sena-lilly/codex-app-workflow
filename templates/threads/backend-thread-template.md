# Backend Thread Template

Copy the prompt below into a new Codex thread for focused backend, FastAPI, API, database, auth, or migration work.

```md
# Backend Thread Prompt

## Thread purpose

Work on one focused backend task while protecting API compatibility, data safety, auth behavior, and rollback options.

## When to create this thread

Create a backend thread when the task involves:

- FastAPI routes, dependencies, schemas, or services
- API contract changes
- Database models, queries, migrations, or seed data
- Environment variables or `.env` handling
- Authentication, authorization, sessions, or tokens
- Mutation safety for create/update/delete operations
- Backend tests, integration tests, or rollback planning
- iOS/backend compatibility

## What context to include

Include:

- Goal
- Service or app name
- Affected routes, schemas, models, services, tasks, or migrations
- API contract expectations
- Auth requirements
- Environment assumptions
- Database and migration context
- Test command if known
- Rollback expectation

## What not to include

Do not include:

- Real production credentials or tokens
- Production database URLs or records
- Customer data
- Full previous transcript
- iOS UI details unless they affect the API contract
- Deployment instructions to run automatically

## Allowed scope

Allowed work:

- Inspect backend code, tests, schemas, migrations, and config
- Implement scoped backend changes
- Add or update tests
- Run safe local tests and dry-runs
- Prepare migration/deploy commands for human approval
- Document rollback and compatibility risks

## Out-of-scope items

Do not:

- Modify production data
- Run production migrations
- Send external API calls
- Deploy services
- Rotate secrets
- Push to GitHub
- Change iOS app behavior unless explicitly requested

## Safety rules

Do not perform these without explicit human confirmation:

- Production database writes or migrations
- External API sends, emails, notifications, or webhooks
- GitHub push, git tag, or GitHub release creation
- Release creation, deployment, or package publishing
- App Store submission or TestFlight submission
- Billing, subscription, IAP, signing, or provisioning changes
- Destructive file, infrastructure, or data operations

If a side-effect operation is needed, stop and present:

- target command / endpoint / screen
- payload or operation details
- impact scope
- rollback plan

## Required first actions

1. Identify affected routes, schemas, models, services, migrations, and tests.
2. Inspect env/config handling and confirm no real secrets are needed.
3. Identify auth and authorization boundaries.
4. Identify mutation paths and data safety risks.
5. Identify API contract impact for iOS or external clients.
6. State the minimal plan before editing.
7. Identify safe local checks, tests, and dry-runs.

## Output format

Return exactly these sections:

## Goal

## Backend Context

Include service, routes, schemas, models, migrations, auth, and env notes.

## Investigation

## API Contract Impact

## Data / Migration / Mutation Safety

## Minimal Plan

## Changes Made

## Tests / Checks Run

For each check include:
- command
- result
- notes

## Rollback Plan

## Files Changed

## Risks / Follow-ups

## Human Confirmation Needed

For each item include:
- target command / endpoint / screen
- payload or operation details
- impact scope
- rollback plan

## Handoff format

End with:

## Goal

## Current State

## Completed

## Not Completed

## Important Decisions

## Files Changed

## Commands Run

## Checks / Verification

## Known Issues / Risks

## Next Prompt

## Done criteria

This backend thread is done when:

- API contract impact is clear.
- Auth, env, mutation safety, database, and migration risks are checked where relevant.
- Tests or dry-runs are run, or blocked checks are documented.
- Rollback plan is stated.
- No production mutation, deployment, or external send was executed without confirmation.
- A handoff is provided.
```
