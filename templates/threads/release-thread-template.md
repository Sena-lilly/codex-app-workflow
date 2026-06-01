# Release Thread Template

Copy the prompt below into a new Codex thread for release readiness, TestFlight, App Store, backend release, or go/no-go work.

```md
# Release Thread Prompt

## Thread purpose

Assess release readiness, separate blockers from acceptable risks, prepare human-confirmation gates, and provide a go/no-go recommendation.

## When to create this thread

Create a release thread when the work involves:

- iOS release readiness
- Backend release readiness
- Combined app/backend release
- App Store review preparation
- TestFlight internal or external testing
- Privacy labels, permission prompts, tracking, or account deletion
- IAP, subscription, StoreKit, pricing, restore purchase, or entitlement risk
- Review notes, tester notes, release notes, known issues, version/build, or rollback

## What context to include

Include:

- Release target
- Version/build
- Release scope
- Target channel: TestFlight, App Store, backend staging, backend production, docs, or GitHub release
- QA status
- Known issues
- Privacy and IAP context
- Migration or backend compatibility context
- Release commands or manual screens expected
- Rollback or mitigation plan

## What not to include

Do not include:

- Secrets, signing credentials, private Apple account details, or production tokens
- Full previous transcript
- Unverified release claims
- Commands that should be executed automatically
- Customer data or production database values

## Allowed scope

Allowed work:

- Inspect release files, docs, checklists, version/build metadata, configs, and notes
- Identify blockers and non-blocking risks
- Prepare release commands/manual steps for human approval
- Review App Store, TestFlight, privacy, IAP, and backend readiness
- Provide go/no-go recommendation

## Out-of-scope items

Do not:

- Upload builds
- Submit to TestFlight
- Submit to App Store review
- Deploy backend services
- Push tags or create GitHub releases
- Send release announcements
- Change pricing, IAP, signing, or provisioning without approval

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

1. Confirm release target, version/build, scope, and channel.
2. Inspect release notes, review notes, known issues, checklists, and version/build files.
3. Check for debug code, localhost URLs, staging/prod config, secrets, and signing/release config risks.
4. Check privacy, IAP, App Store, TestFlight, and backend migration risks.
5. Confirm QA evidence and unresolved blockers.
6. Prepare release actions for human confirmation but do not execute them.
7. Produce GO / GO WITH RISKS / NO-GO.

## Output format

Return exactly these sections:

## Release Target

## Scope And Version

## Readiness Status

Use one:
- GO
- GO WITH RISKS
- NO-GO

## Blocking Issues

## Non-Blocking Risks

## QA / Verification Status

## App Store / TestFlight Readiness

## Backend / Migration Readiness

## Privacy / IAP / Metadata Readiness

## Known Issues

## Prepared Actions Not Run

For each action include:
- target command / endpoint / screen
- payload or operation details
- impact scope
- rollback plan

## Human Confirmation Needed

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

This release thread is done when:

- Release target, channel, version/build, and scope are clear.
- iOS/backend/App Store/TestFlight/privacy/IAP/review notes/migration risks are checked where relevant.
- GO/GO WITH RISKS/NO-GO is stated with evidence.
- Human-confirmation items are prepared but not executed.
- Rollback or mitigation is documented.
- A handoff is provided.
```
