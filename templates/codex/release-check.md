# Codex Template: Release Check

Copy the prompt below into Codex before any App Store, TestFlight, iOS release, backend release, upload, submission, deployment, or public release step.

```md
# Release Check Prompt

## Purpose

Assess release readiness across iOS build configuration, TestFlight/App Store preparation, privacy, IAP, backend compatibility, migration risk, known issues, and human confirmation gates.

## When to use

Use this before:

- Creating a release build
- Archiving an iOS app
- Uploading to App Store Connect
- Preparing TestFlight distribution
- Preparing App Store review
- Deploying a backend service
- Creating a GitHub release or public announcement

## Required inputs

Release target:
- [iOS app / backend service / combined release / docs release]

Version/build:

Bundle ID or service name:

Release scope:
- 

Target channel:
- [internal TestFlight / external TestFlight / App Store / backend staging / backend production / GitHub release]

Known issues:
- 

QA status:

Rollback plan:

Files or docs to inspect:
- 

## Pre-checks

Before giving a go/no-go recommendation:

- Inspect release notes, version/build files, app config, release config, privacy docs, IAP docs, backend migration notes, and checklists if present.
- Check Release build, version/build number, Bundle ID, signing, entitlements, capabilities, localhost/Debug config, secrets, API endpoint, crash risk, device testing, and watchOS companion if applicable.
- Check App Store review metadata, TestFlight readiness, privacy answers, IAP/subscriptions, review notes, tester notes, known issues, and rollback plan.
- Check backend compatibility, migrations, feature flags, and production/staging environment risk if backend is involved.
- Treat missing evidence as `unknown` or `blocker`.

## Checklist

Review these items:

- Release build configuration is confirmed.
- Version/build number is correct and unique.
- Bundle ID or service identifier is correct.
- Signing, entitlements, and capabilities are reviewed.
- Localhost, Debug flags, mock data, and verbose logging are checked.
- Secrets, tokens, `.env`, signing files, and production credentials are not committed.
- API endpoint is correct for the release channel.
- Crash risk and crash reporting are reviewed.
- Device testing is completed or gaps are documented.
- watchOS companion, widgets, extensions, or companion targets are checked if applicable.
- App Store metadata and review notes are ready if App Store is involved.
- TestFlight instructions, tester groups, and Beta App Review notes are ready if TestFlight is involved.
- Privacy policy, App Privacy answers, tracking, analytics, crash logs, identifiers, and third-party SDKs are reviewed.
- IAP/subscription products, restore purchases, entitlement handling, and sandbox behavior are reviewed.
- Backend migrations, data compatibility, rollout, and rollback are reviewed.
- Known issues are classified as blocker or non-blocking risk.

## Safety rules

Do not perform these actions:

- Upload builds
- Submit to TestFlight
- Submit to App Store review
- Deploy backend services
- Push tags or create GitHub releases
- Send release announcements
- Change App Store Connect settings
- Change pricing, IAP, subscriptions, signing, provisioning, or availability
- Send external API requests
- Modify production data

If a release action is needed, document it only and present:

- target command / endpoint / screen
- payload or operation details
- impact scope
- rollback plan

## Output format

Return exactly these sections:

## Release Readiness Status

Use one:
- GO
- GO WITH RISKS
- NO-GO

## Release Target / Scope / Version

## iOS Build Readiness

## TestFlight Readiness

## App Store Readiness

## Privacy Readiness

## IAP / Subscription Readiness

## Backend / Migration Readiness

## Known Issues

## Common Blockers Found

## Required Fixes

## Non-Blocking Risks

## Release Actions Prepared But Not Run

For each action include:
- target command / endpoint / screen
- payload or operation details
- impact scope
- rollback plan

## Human Confirmation Needed

## Done criteria

This release check is done only when:

- Release target, channel, scope, version/build, and rollback plan are clear.
- iOS build, App Store, TestFlight, privacy, IAP, backend, migration, and known issue risks are checked where relevant.
- Blockers and non-blocking risks are separated.
- A go/no-go recommendation is provided.
- Release actions are documented but not executed.

## Common blockers

- Release build configuration not confirmed
- Bundle ID, signing, entitlement, or capability mismatch
- Localhost, Debug, mock data, secrets, or wrong API endpoint present
- Missing privacy policy or inaccurate App Privacy answers
- IAP products, pricing, restore purchases, or entitlement behavior unclear
- App Store review notes, demo account, or screenshots missing
- TestFlight tester instructions or Beta App Review notes missing
- Migration or backend rollback plan missing
- Known crash or release-blocking issue unresolved
```
