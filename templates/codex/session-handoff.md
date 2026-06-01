# Codex Template: Session Handoff

Copy the prompt below into Codex at the end of a session or before switching threads.

```md
# Session Handoff Prompt

## Purpose

Create a compact, accurate handoff so another Codex thread or human developer can continue without reading the full conversation.

## When to use

Use this when:

- Ending a Codex session
- Switching from investigation to implementation
- Splitting iOS, backend, release, QA, or legal review work into another thread
- Pausing before a side-effect operation that requires human approval
- Preparing the next prompt for a follow-up thread

## Inputs

Session goal:

Original request:

Current state:

Target next thread:
- [iOS / backend / release / bugfix / QA / legal / docs / unknown]

Anything the next thread must not do:

## Constraints

- Be concise but specific.
- Do not hide failed checks or uncertainty.
- Separate completed work from incomplete work.
- Include exact file paths and commands where available.
- Include the next prompt as something the human can paste directly into Codex.
- Do not perform new implementation work while creating the handoff.

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

Before writing the handoff, confirm:

- Goal and current state
- Completed items
- Not completed items
- Important decisions and why they were made
- Files changed
- Commands run and results
- Tests/checks passed, failed, skipped, or blocked
- Known issues, risks, and unknowns
- Side-effect operations that still need human confirmation
- Best next prompt for continuation

## Work order

1. Review what was requested.
2. Review what changed and what was verified.
3. Separate facts from assumptions.
4. Identify incomplete work and risks.
5. Write the next prompt for the most useful follow-up thread.

## Output format

Return exactly these sections:

## Goal

## Current State

## Completed

## Not Completed

## Important Decisions

For each decision include:
- decision
- reason
- tradeoff

## Files Changed

For each file include:
- path
- purpose of change

## Commands Run

For each command include:
- command
- result
- notes

## Checks / Verification

## Known Issues / Risks

## Human Confirmation Needed

For each item include:
- target command / endpoint / screen
- payload or operation details
- impact scope
- rollback plan

## Next Prompt

Provide a ready-to-paste prompt for the next Codex thread.

## Done criteria

The handoff is done only when:

- Goal and current state are understandable without prior chat context.
- Completed and not completed work are clearly separated.
- Files changed and commands run are listed.
- Known issues and verification gaps are explicit.
- Any side-effect operation is listed but not executed.
- The next prompt is concrete enough to continue work immediately.
```
