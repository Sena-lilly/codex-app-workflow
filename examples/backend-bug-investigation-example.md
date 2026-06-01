# Backend Bug Investigation Example

This example shows how to use Codex for a backend bug investigation with root-cause analysis before applying a fix.

## Scenario

`Sample Booking App` has a FastAPI backend. Users report that cancelling a booking sometimes returns success, but the booking still appears as active in the app.

The issue may involve route logic, database mutation behavior, auth ownership checks, or a stale API response.

## Goal

Reproduce or reason through the bug, identify root cause, propose fix options, apply only the minimal safe fix if clear, and run regression checks.

## Starting prompt

Paste this into a new Codex thread:

```md
Use templates/threads/backend-thread-template.md and templates/codex/bug-investigation.md.

App:
Sample Booking App

Bug summary:
Cancelling a booking sometimes returns success, but the booking remains active.

Observed behavior:
The API response indicates cancellation succeeded. The booking still appears in active bookings.

Expected behavior:
After cancellation succeeds, the booking should no longer appear as active.

Reproduction steps:
1. Create a booking using local test data.
2. Cancel the booking through the local API route.
3. Fetch active bookings for the same user.

Environment:
- Backend: FastAPI local development environment
- Database: local test database only
- External services: none

Constraints:
- Do not connect to production.
- Do not run production migrations.
- Do not send external API requests.
- Do not deploy.
- Do not push to GitHub.

Safety:
If a side-effect operation is needed, stop and present target, payload, impact scope, and rollback.
```

## Recommended template

- [Backend thread template](../templates/threads/backend-thread-template.md)
- [Bug investigation template](../templates/codex/bug-investigation.md)
- [Session handoff template](../templates/codex/session-handoff.md)

## Expected workflow

1. Inspect route, schema, model, service, and tests for booking cancellation.
2. Identify mutation path and auth/ownership checks.
3. Check whether active bookings query filters cancelled records.
4. Reproduce using local tests or reason from existing test fixtures.
5. Compare suspected causes with evidence.
6. State root cause or mark it unproven.
7. Apply the smallest fix only if root cause is clear.
8. Add regression test for cancelled bookings not appearing as active.

## Expected output

```md
## Bug Summary

Cancellation returns success, but cancelled bookings can remain in active booking results.

## Reproduction Status

Reproduced in local test using local fixture data.

## Observed vs Expected

Observed:
Cancelled booking remains in active bookings response.

Expected:
Cancelled booking is excluded from active bookings response.

## Evidence Reviewed

- cancellation route
- booking service mutation logic
- active bookings query
- booking status enum
- existing API tests

## Suspected Causes

- hypothesis: Cancellation mutation does not persist status.
- evidence for: none after inspecting service save path
- evidence against: cancellation test confirms status is updated
- confidence: low

- hypothesis: Active bookings query does not exclude cancelled status.
- evidence for: query filters by date but not status
- evidence against: none
- confidence: high

## Root Cause

The active bookings query did not exclude cancelled bookings.

## Fix Options

- option: Add cancelled-status exclusion to active bookings query.
- risk: low, scoped to active bookings endpoint.
- verification: regression test for cancelled booking exclusion.
- rollback: revert query and test changes.

## Minimal Fix Applied

Added status filter to active bookings query and regression test.

## Files Changed

- [path]: active bookings query
- [path]: API regression test

## Checks Run

- command: [local backend test command]
- result: pass
- notes: cancellation regression test passed

## Remaining Uncertainty

No production data was inspected. Production impact should be assessed separately by a human owner if needed.

## Human Confirmation Needed

None for local fix. Production deployment or migration would require confirmation.
```

## Handoff example

```md
## Goal

Investigate cancellation bug in Sample Booking App backend.

## Current State

Root cause identified and minimal local fix applied.

## Completed

- Inspected cancellation route and active bookings query.
- Reproduced issue with local test data.
- Added regression coverage.

## Not Completed

- No deployment.
- No production data inspection.
- No production migration.

## Important Decisions

- decision: Fix active bookings query only.
- reason: Root cause was query filtering, not cancellation mutation.
- tradeoff: Historical data cleanup was not included.

## Files Changed

- [path]: query filter
- [path]: regression test

## Commands Run

- [local backend test command]: pass

## Checks / Verification

Regression test confirms cancelled bookings are excluded from active results.

## Known Issues / Risks

Need release manager review before any backend deployment.

## Human Confirmation Needed

Backend deployment requires target, payload, impact scope, and rollback.

## Next Prompt

Use templates/agents/qa-agent.md to verify cancellation flow and regression cases.
```

## Common mistakes

- Fixing cancellation mutation before proving the failing boundary.
- Running against production data.
- Ignoring auth/ownership checks.
- Shipping without a regression test.
- Treating a successful API response as proof that all downstream queries are correct.

## Done criteria

- Reproduction status is clear.
- Root cause is evidence-based.
- Minimal fix is applied only if root cause is proven.
- Regression test exists or blocked verification is documented.
- No production mutation, external send, deployment, or GitHub push occurred.
- Handoff records root-cause analysis.
