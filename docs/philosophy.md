# Philosophy

`codex-app-workflow` is built around one idea:

Codex should help developers move faster without making irreversible decisions on their behalf.

## Principles

### 1. Human Confirmation for Real-World Side Effects

Codex can propose commands, inspect code, run local checks, and prepare release steps. It must not silently perform operations that affect production systems, customers, billing, public repositories, or app distribution.

Any side-effect operation requires explicit human confirmation with:

- target
- payload or operation details
- impact scope
- rollback plan, recovery path, revert method, and known limitations

### 2. Root Cause Before Broad Changes

When debugging, Codex should first explain what is known, what is unknown, and what evidence is needed.

Good investigation work includes:

- Reproduction steps
- Relevant logs or errors
- Suspected failure boundary
- Root cause hypothesis
- Minimal fix
- Regression checks

### 3. Small Threads, Clear Handoffs

Large Codex sessions become hard to reason about. Work should be split by domain, responsibility, or risk.

Useful thread boundaries include:

- iOS UI and SwiftUI work
- Backend and API work
- Bug investigation
- Release preparation
- App Store or TestFlight review
- Legal, privacy, or safety review

Every meaningful session should end with a handoff.

### 4. Templates Are Starting Points

The templates in this repository are not rigid scripts. They are starting points that should be adapted to the project, team, release stage, and risk level.

Keep the structure. Change the details.

### 5. Codex Should Verify Its Work

Whenever possible, a Codex workflow should include verification:

- Run tests
- Build the app
- Check formatting or linting
- Inspect changed files
- Reproduce the bug
- Confirm release metadata
- Validate privacy and permission copy

If verification cannot be completed, the handoff should say why.

### 6. Documentation Is Part of the Product

Codex workflows are easier to trust when decisions are visible. This project treats prompts, checklists, handoffs, and release notes as first-class development artifacts.
