# Codex Template: Refactor Safely

Copy the prompt below into Codex when behavior must remain unchanged.

```md
# Refactor Safely Prompt

## Purpose

Improve structure, readability, maintainability, or duplication while preserving existing behavior.

## When to use

Use this when:

- The desired outcome is cleanup, extraction, renaming, modularization, or simplification
- User-visible behavior must not change
- Public APIs, schemas, and release behavior should remain stable
- The work may touch iOS, backend, shared models, tests, or docs

## Inputs

Refactor goal:

Why this refactor is needed:

Behavior that must stay the same:
- 
- 
- 

Allowed files or directories:
- 

Do-not-touch files or directories:
- 

Public APIs, schemas, or contracts that must not change:
- 

Current tests/checks available:
- 

Rollback expectation:
- 

## Constraints

- Behavior-preserving rule: do not intentionally change user-visible behavior, API behavior, persistence behavior, release behavior, or billing behavior.
- Do not change public APIs, database schemas, migrations, API contracts, analytics events, IAP identifiers, signing, provisioning, or release config unless explicitly approved.
- Inspect existing tests before editing.
- Prefer small mechanical steps over broad rewrites.
- Avoid unrelated formatting churn.
- Stop if the refactor requires a product decision.

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

- Identify behavior boundaries.
- Identify public APIs, schemas, migrations, config, and generated files.
- Run or record baseline tests/checks where practical.
- Identify the smallest safe sequence of changes.

After editing:

- Run the same checks as before, where possible.
- For iOS: consider build/tests, snapshots/UI smoke checks, localization and permission strings.
- For backend: consider unit tests, route tests, schema compatibility, migration dry-run, lint/type checks.
- Confirm public APIs, schemas, migrations, and release settings are unchanged unless explicitly approved.
- Summarize the diff by behavior-preserving category.

## Work order

1. Restate the refactor goal and behavior-preserving requirements.
2. Inspect relevant files and tests.
3. Record baseline checks before changes when practical.
4. Propose the minimal refactor sequence.
5. Apply small, reviewable changes.
6. Run after-change checks.
7. Compare before/after behavior evidence.
8. Provide rollback instructions.

## Output format

Return exactly these sections:

## Refactor Goal

## Behavior-Preserving Requirements

## Investigation

## Baseline Checks

For each check include:
- command
- result
- notes

## Proposed Minimal Diff

## Changes Made

## Public API / Schema / Config Impact

## Files Changed

## After-Change Checks

For each check include:
- command
- result
- notes

## Diff Summary

Group changes by category, such as rename, extraction, deduplication, test update, docs update.

## Rollback Plan

## Risks / Follow-ups

## Human Confirmation Needed

For each item include:
- target command / endpoint / screen
- payload or operation details
- impact scope
- rollback plan

## Done criteria

The refactor is done only when:

- Behavior-preserving requirements are satisfied.
- Public APIs, schemas, migrations, release config, and billing identifiers are unchanged unless explicitly approved.
- Before/after checks are run or blocked checks are documented.
- The diff is scoped and reviewable.
- Rollback is described.
- No side-effect operation was executed without human confirmation.
```
