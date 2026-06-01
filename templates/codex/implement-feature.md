# Codex Template: Implement Feature

Copy the prompt below into Codex when a feature is ready to implement.

```md
# Implement Feature Prompt

## Purpose

Implement one scoped feature with a minimal diff, clear verification, and no unrelated changes.

## When to use

Use this when:

- The feature goal is known
- Acceptance criteria can be stated
- The allowed change area is clear or can be discovered
- The work may touch iOS, backend, shared models, tests, docs, or release notes

## Inputs

Feature:

User value:

Acceptance criteria:
- 
- 
- 

Allowed files or directories:
- 

Do-not-touch files or directories:
- 

Relevant platforms:
- [iOS / backend / release config / docs / other]

Known constraints:
- 

Test plan expected by human:
- 

Rollback expectation:
- 

## Constraints

- Inspect relevant files before editing.
- Do not start implementation until you can state the target files and likely diff.
- Keep the diff minimal and scoped to the feature.
- Follow existing architecture, naming, style, and test patterns.
- Do not combine refactors with feature work unless required for the feature.
- Do not change public APIs, schemas, migrations, signing, provisioning, billing, or release configuration unless the acceptance criteria explicitly require it.
- If the requested feature conflicts with existing behavior, stop and explain the conflict before editing.

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

Before editing:

- Identify relevant files and ownership boundaries.
- Identify tests or checks that should cover the feature.
- Identify any data, API, migration, auth, privacy, IAP, or release risk.
- Identify files that must not be touched.

After editing:

- Run the smallest meaningful local verification available.
- For iOS: consider build, unit tests, UI tests, previews, asset checks, permission strings, localhost/API config.
- For backend: consider unit tests, route tests, schema validation, migration dry-run, lint/type checks.
- For release-sensitive changes: consider version/build, release notes, privacy text, IAP behavior, debug flags, secrets, localhost.
- If checks cannot run, explain why and give the exact command the human should run.

## Work order

1. Restate the goal and acceptance criteria.
2. Inspect relevant code, tests, docs, and configuration.
3. Report the proposed file list and minimal diff plan.
4. Identify risks and rollback approach before editing.
5. Implement the smallest safe change.
6. Run required checks.
7. Summarize the diff, verification, and remaining risks.

## Output format

Return exactly these sections:

## Goal

## Acceptance Criteria

## Investigation

Include files inspected and important findings.

## Proposed Minimal Diff

Include files expected to change before editing.

## Changes Made

## Files Changed

## Checks Run

For each check include:
- command
- result
- notes

## Acceptance Criteria Status

Mark each criterion as:
- met
- partially met
- not met

## Rollback Plan

## Risks / Follow-ups

## Human Confirmation Needed

For each item include:
- target command / endpoint / screen
- payload or operation details
- impact scope
- rollback plan

## Done criteria

The feature is done only when:

- The implemented change maps directly to the acceptance criteria.
- The diff is minimal and avoids prohibited files.
- Relevant local checks have passed, or blocked checks are clearly documented.
- Rollback is described.
- No side-effect operation was executed without human confirmation.
```
