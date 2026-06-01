# Session Handoff Example

This example shows how to end a release thread with a concise handoff that another Codex thread can continue.

## Scenario

`Sample Wellness App` completed an App Store readiness review for version `1.2.0`. The release thread found no hard blocker, but privacy answers, screenshots, and wellness wording still need human review.

## Goal

Create a release thread handoff that clearly separates completed work, incomplete work, decisions, risks, human-confirmation items, and the next prompt.

## Starting prompt

Paste this into the same Codex thread before ending it:

```md
Use templates/codex/session-handoff.md.

Create a session handoff for this release readiness thread.

Session goal:
Review Sample Wellness App 1.2.0 for App Store readiness.

Current state:
Release readiness review is complete. No App Store Connect, TestFlight, GitHub, external API, or production operation was executed.

Include:
- completed review areas
- not completed areas
- important decisions
- files changed
- commands run
- checks and verification
- known issues and risks
- human confirmation needed
- next prompt for legal/privacy review
```

## Recommended template

- [Session handoff template](../templates/codex/session-handoff.md)
- [Release thread template](../templates/threads/release-thread-template.md)
- [Legal review agent](../templates/agents/legal-review-agent.md)

## Expected workflow

1. Restate the release thread goal.
2. Summarize current readiness state.
3. Separate completed and not completed items.
4. Record important decisions and tradeoffs.
5. List files changed and commands run.
6. List known issues and risks.
7. List human-confirmation items.
8. Write a ready-to-paste next prompt.

## Expected output

```md
## Goal

Review Sample Wellness App 1.2.0 for App Store readiness.

## Current State

Release readiness review is complete. No external operation was executed.

## Completed

- Reviewed release scope.
- Reviewed App Store metadata checklist.
- Reviewed TestFlight/App Store operation risks.
- Reviewed privacy and wellness claim risks.
- Prepared App Store Connect action notes without executing them.

## Not Completed

- Human visual review of screenshots.
- Human verification of App Privacy answers.
- Legal review of wellness wording.
- Final App Store submission.

## Important Decisions

- decision: GO WITH RISKS
- reason: No local blocker found, but human review remains.
- tradeoff: Release can continue only after privacy, screenshot, and wellness copy risks are accepted.

## Files Changed

- None in the app project.

## Commands Run

- Local file inspection only.

## Checks / Verification

- App Store metadata reviewed.
- Privacy checklist reviewed.
- IAP risk marked not applicable for this scenario.
- Health/medical claim risk identified for wording review.

## Known Issues / Risks

- Placeholder URLs must be verified by the human owner.
- Wellness copy must avoid diagnosis, treatment, cure, or guaranteed results.
- App Privacy answers must match analytics and crash reporting.

## Human Confirmation Needed

- target: App Store Connect submission screen
- payload or operation details: submit Sample Wellness App 1.2.0 for review
- impact scope: public App Store review process and release timeline
- rollback: cancel submission if possible, edit metadata before review, or reject the build from release flow; known limitation: review history may remain visible in App Store Connect

## Next Prompt

Use templates/agents/legal-review-agent.md.

Review Sample Wellness App 1.2.0 wellness copy and privacy disclosures.

Focus on:
- privacy policy alignment
- App Privacy answers
- analytics and crash reporting disclosure
- wellness wording
- medical/health/effectiveness claims
- App Store review risk

Do not change App Store Connect, submit the app, send external API requests, push to GitHub, or modify production data.
```

## Handoff example

The `Expected output` section above is the handoff example. It is intentionally short enough to paste into a follow-up legal/privacy thread.

## Common mistakes

- Writing a narrative summary without next actions.
- Hiding incomplete work.
- Omitting commands run.
- Omitting human-confirmation requirements.
- Saying "ready" without naming remaining risks.
- Forgetting the next prompt.

## Done criteria

- The next thread can continue without reading the full previous conversation.
- Completed and not completed work are separated.
- Human-confirmation items include target, payload, impact scope, and rollback.
- Next prompt is ready to paste.
- No release, App Store, TestFlight, GitHub, external API, or production operation was executed.
