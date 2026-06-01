# iOS Feature Example

This example shows how to use Codex for a scoped SwiftUI feature without touching release settings or backend behavior.

## Scenario

`Sample Habit App` has a SwiftUI habit detail screen. The user wants to add a lightweight "Mark as skipped today" action so a habit can be skipped without counting as completed.

The app already has local habit state, a detail view, and unit tests for habit status rules.

## Goal

Implement the smallest iOS-side change that adds a skip action, updates the UI state, and verifies behavior locally.

## Starting prompt

Paste this into a new Codex thread:

```md
Use templates/threads/ios-thread-template.md and templates/codex/implement-feature.md.

App:
Sample Habit App

Goal:
Add a "Skip today" action to the habit detail screen.

Acceptance criteria:
- The habit detail screen shows a skip action when today's habit is not completed.
- Tapping skip marks today as skipped, not completed.
- Skipped days are visually distinct from completed days.
- Existing complete/uncomplete behavior still works.

Allowed files/directories:
- iOS app source files related to habit detail UI and habit status logic
- Existing local tests for habit status

Do-not-touch files/directories:
- Signing, provisioning, App Store, TestFlight, and release settings
- Backend/API code
- Production config

Safety:
Do not push to GitHub, upload builds, submit releases, contact external APIs, or modify production data.
If any side-effect operation is needed, stop and present target, payload, impact scope, and rollback.
```

## Recommended template

- [iOS thread template](../templates/threads/ios-thread-template.md)
- [Implement feature template](../templates/codex/implement-feature.md)
- [Session handoff template](../templates/codex/session-handoff.md)

## Expected workflow

1. Inspect SwiftUI habit detail files and habit status model.
2. Identify existing tests around complete/uncomplete behavior.
3. Confirm no release, signing, StoreKit, App Store, or backend files are needed.
4. Propose a minimal diff before editing.
5. Add the skipped state/action using existing patterns.
6. Run targeted local tests if available.
7. Summarize changed files, checks, and rollback.

## Expected output

```md
## Goal

Add a "Skip today" action to Sample Habit App's habit detail screen.

## Investigation

- Found habit detail UI in [local path].
- Found habit status model in [local path].
- Found existing tests for complete/uncomplete behavior in [local path].
- No backend, signing, App Store, or TestFlight files are required.

## Minimal Diff Plan

- Add skipped status handling to the local habit status model.
- Add a skip action in the habit detail view.
- Add or update focused tests for skipped vs completed behavior.

## Changes Made

- Added skip action.
- Preserved existing complete/uncomplete flow.
- Added skipped visual state.

## Files Changed

- [path]: habit status logic
- [path]: habit detail view
- [path]: focused tests

## Checks Run

- command: [local test command]
- result: pass
- notes: targeted habit status tests passed

## Acceptance Criteria Status

- Skip action appears when today's habit is not completed: met
- Tapping skip marks today as skipped, not completed: met
- Skipped days are visually distinct: met
- Existing complete/uncomplete behavior still works: met

## Rollback Plan

Revert the changed habit status, detail view, and test files.

## Human Confirmation Needed

None. No side-effect operation was required.
```

## Handoff example

```md
## Goal

Add a "Skip today" action to Sample Habit App.

## Current State

Implementation is complete locally.

## Completed

- Inspected relevant SwiftUI and habit status files.
- Added skip action and skipped state.
- Ran targeted local checks.

## Not Completed

- No release build or TestFlight work was attempted.

## Important Decisions

- decision: Keep the change iOS-local.
- reason: Acceptance criteria did not require backend sync.
- tradeoff: Backend-backed skip history can be considered later.

## Files Changed

- [path]: habit status logic
- [path]: habit detail UI
- [path]: tests

## Commands Run

- [local test command]: pass

## Checks / Verification

Targeted tests passed.

## Known Issues / Risks

Backend sync is not implemented.

## Human Confirmation Needed

None.

## Next Prompt

Use templates/agents/qa-agent.md to review skipped/completed behavior and edge cases.
```

## Common mistakes

- Mixing feature work with release settings.
- Adding backend sync before the local behavior is proven.
- Changing unrelated SwiftUI views.
- Skipping tests because the UI change looks small.
- Forgetting rollback notes.

## Done criteria

- The feature maps directly to acceptance criteria.
- Diff is limited to iOS feature files and tests.
- No signing, App Store, TestFlight, backend, or production config files are changed.
- Local verification is run or blocked checks are documented.
- Handoff is ready for QA.
