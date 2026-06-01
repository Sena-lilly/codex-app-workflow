# Codex Template: Bug Investigation

Copy the prompt below into Codex when the root cause is not yet proven.

```md
# Bug Investigation Prompt

## Purpose

Investigate a bug from evidence to root cause before proposing or applying a minimal fix.

## When to use

Use this when:

- Behavior differs from expected behavior
- The reproduction path is unclear
- Logs, screenshots, stack traces, or user reports need interpretation
- A fix is tempting but the root cause is not yet proven
- The issue may cross iOS, backend, API, database, release, or configuration boundaries

## Inputs

Bug summary:

Observed behavior:

Expected behavior:

Reproduction steps:
1. 
2. 
3. 

Environment:
- App version/build:
- Device/OS/browser:
- Backend environment:
- Account/test data:
- Network state:

Logs/errors/screenshots:

Recent changes or suspected area:

Files or areas that must not be changed:

## Constraints

- Do not fix before stating the likely root cause and evidence.
- Do not rewrite broad areas to see if the bug disappears.
- Prefer reproduction, logs, tests, and code-path tracing over guesses.
- Keep any fix minimal and tied to the proven cause.
- If the bug involves production data, auth, billing, IAP, privacy, or release behavior, treat it as high risk.
- If evidence is insufficient, stop with questions or a targeted evidence request.

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

Investigate:

- Reproduction status: reproduced, not reproduced, or reasoned from evidence
- Observed vs expected behavior
- Logs, stack traces, screenshots, and error messages
- Relevant code paths and ownership boundary
- API request/response assumptions
- Localhost, environment, feature flag, and secret/config assumptions
- Database state or migration assumptions, using dry-run or local data only
- Recent changes that could explain the regression
- Test coverage that should have caught the bug

After a fix, run targeted regression checks. If no fix is applied, list the exact checks or evidence still needed.

## Work order

1. Restate observed and expected behavior.
2. Validate or reconstruct reproduction steps.
3. Inspect logs and relevant code paths.
4. List suspected causes with evidence for and against each.
5. Identify the most likely root cause.
6. Propose fix options, including the smallest safe option.
7. Implement only the minimal fix if the cause is clear and the user requested implementation.
8. Run targeted regression checks.

## Output format

Return exactly these sections:

## Bug Summary

## Reproduction Status

## Observed vs Expected

## Evidence Reviewed

## Suspected Causes

For each cause include:
- hypothesis
- evidence for
- evidence against
- confidence

## Root Cause

State if unproven.

## Fix Options

For each option include:
- change
- risk
- verification
- rollback

## Minimal Fix Applied

Use "None" if no fix was applied.

## Files Changed

## Checks Run

For each check include:
- command
- result
- notes

## Remaining Uncertainty

## Human Confirmation Needed

For each item include:
- target command / endpoint / screen
- payload or operation details
- impact scope
- rollback plan

## Done criteria

The investigation is done only when:

- Reproduction status is clear.
- Observed and expected behavior are recorded.
- Suspected causes are compared with evidence.
- Root cause is stated or explicitly marked unproven.
- Any applied fix is minimal and tied to the root cause.
- Targeted checks are run or documented as blocked.
- No side-effect operation was executed without human confirmation.
```
