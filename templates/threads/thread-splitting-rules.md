# Thread Splitting Rules

Copy the prompt below into Codex when deciding whether to continue in the current thread or start a new focused thread.

```md
# Thread Splitting Decision Prompt

## Thread purpose

Decide whether the current Codex work should stay in this thread or split into a new thread, then prepare the handoff and next prompt if a split is needed.

## When to create this thread

Use this decision prompt when:

- The topic changes domain: iOS, backend, bugfix, release, QA, audit, legal, privacy, or docs
- A feature implementation turns into a bug investigation
- A bug investigation becomes a fix
- Implementation becomes release readiness
- Release work involves App Store, TestFlight, backend deployment, privacy, IAP, or migration risk
- Security/privacy audit work needs focus
- The conversation is too long to summarize safely
- Context overflow is likely or important decisions are becoming hard to track

## What context to include

Include:

- Current goal
- Current status
- Domain involved: feature / bugfix / release / audit / iOS / backend / QA / legal
- Files changed
- Commands run and results
- Decisions made
- Risks, unknowns, and blockers
- Acceptance criteria or release criteria
- Links to relevant templates, especially `templates/codex/session-handoff.md`

## What not to include

Do not include:

- Full chat transcripts unless essential
- Secrets, tokens, private keys, credentials, or real customer data
- Unrelated brainstorming
- Unverified assumptions presented as facts
- Release commands to execute automatically
- Production database values or private environment variables

## Allowed scope

Allowed work:

- Decide whether to split or continue
- Recommend the next thread type
- Prepare a concise handoff
- Prepare a ready-to-paste next prompt
- Identify human-confirmation items

## Out-of-scope items

Do not:

- Implement code
- Run release commands
- Push to GitHub
- Submit to App Store or TestFlight
- Deploy backend services
- Modify production data
- Perform security-sensitive operations

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

1. Identify the current thread's main goal.
2. Identify whether the domain has changed.
3. Check whether the current context can be summarized in under 10 bullets.
4. Check whether feature, bugfix, release, and audit work are mixed together.
5. Decide: continue, split now, or finish with handoff.
6. If splitting, create a handoff using `templates/codex/session-handoff.md`.

## Output format

Return exactly these sections:

## Decision

Use one:
- Continue current thread
- Split now
- Finish current thread with handoff

## Reason

## Current Thread Summary

## Recommended Next Thread Type

Use one:
- iOS
- backend
- bugfix
- release
- QA
- legal/privacy
- security audit
- docs
- no split needed

## Context To Carry Forward

## Context To Leave Behind

## Human Confirmation Needed

For each item include:
- target command / endpoint / screen
- payload or operation details
- impact scope
- rollback plan

## Next Prompt

Provide a ready-to-paste prompt for the next Codex thread.

## Handoff format

When splitting, use this handoff structure:

## Goal

## Current State

## Completed

## Not Completed

## Important Decisions

## Files Changed

## Commands Run

## Checks / Verification

## Known Issues / Risks

## Human Confirmation Needed

## Next Prompt

## Done criteria

This thread split decision is done when:

- The decision to continue or split is explicit.
- Feature, bugfix, release, and audit concerns are separated when needed.
- Context overflow risk has been assessed.
- The handoff is short enough for a new thread to use.
- The next prompt is ready to paste.
- No side-effect operation was executed.
```
