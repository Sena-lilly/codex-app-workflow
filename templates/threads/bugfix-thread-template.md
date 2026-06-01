# Bugfix Thread Template

Copy the prompt below into a new Codex thread for focused bug investigation, root-cause analysis, minimal fix, and regression verification.

```md
# Bugfix Thread Prompt

## Thread purpose

Investigate a bug from observed behavior to root cause, apply only the minimal safe fix when appropriate, and verify regressions.

## When to create this thread

Create a bugfix thread when:

- Observed behavior differs from expected behavior
- Reproduction, logs, or root cause need focused analysis
- A feature thread discovered a bug
- A release thread found a blocker
- iOS/backend/API/config boundaries need tracing
- A fix is tempting but not yet proven

## What context to include

Include:

- Bug summary
- Observed behavior
- Expected behavior
- Reproduction steps
- Environment: app version, device/OS, simulator, backend env, account/test data
- Logs, stack traces, screenshots, or error messages
- Recent changes or suspected causes
- Files or areas already inspected
- Regression checks expected

## What not to include

Do not include:

- Real secrets, tokens, private user data, or customer records
- Full previous transcript
- Broad feature requests unrelated to the bug
- Release execution commands
- Production mutation instructions

## Allowed scope

Allowed work:

- Reproduce or reason through the bug from evidence
- Inspect relevant iOS, backend, API, config, migration, and test files
- Compare suspected causes
- Identify root cause
- Apply minimal fix if root cause is clear
- Run targeted regression checks
- Prepare a handoff

## Out-of-scope items

Do not:

- Make broad rewrites before root cause is clear
- Mix unrelated feature work into the fix
- Deploy fixes
- Modify production data
- Send external API requests
- Push to GitHub
- Submit releases

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

1. Restate observed and expected behavior.
2. Confirm reproduction status: reproduced, not reproduced, or reasoned from evidence.
3. Inspect logs, stack traces, screenshots, and relevant code paths.
4. List suspected causes with evidence for and against each.
5. State root cause or mark it unproven.
6. Propose fix options.
7. Apply only the minimal fix if root cause is clear.
8. Run targeted regression checks.

## Output format

Return exactly these sections:

## Bug Summary

## Observed / Expected

## Reproduction Status

## Evidence Reviewed

## Suspected Causes

For each cause include:
- hypothesis
- evidence for
- evidence against
- confidence

## Root Cause

Use "Unproven" if evidence is insufficient.

## Minimal Fix

## Regression Tests

For each check include:
- command or manual check
- result
- notes

## Files Changed

## Risks / Remaining Uncertainty

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

This bugfix thread is done when:

- Observed and expected behavior are recorded.
- Reproduction status is clear.
- Suspected causes are compared with evidence.
- Root cause is stated or explicitly marked unproven.
- Any fix is minimal and tied to the root cause.
- Regression checks are run or documented as blocked.
- No side-effect operation was executed.
- A handoff is provided.
```
