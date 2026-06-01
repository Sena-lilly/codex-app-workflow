# Release Management

Release work should be calm, explicit, reviewable, and gated by human confirmation.

This guide explains how to use the App Store, TestFlight, iOS release, privacy, IAP, and release-check templates before any submission, upload, deployment, or public release.

## Purpose

Define a practical release workflow for Codex-assisted app development that separates readiness review from real-world release operations.

## When to use

Use this guide when:

- Preparing a release build
- Preparing TestFlight distribution
- Preparing App Store review
- Reviewing privacy or App Privacy answers
- Reviewing IAP/subscriptions
- Coordinating iOS and backend release compatibility
- Deciding whether a release is GO, GO WITH RISKS, or NO-GO

## Required inputs

For every release thread or check, collect:

- Release target: iOS, backend, combined, docs
- Version/build
- Bundle ID or service name
- Release scope
- Target channel: internal TestFlight, external TestFlight, App Store, backend staging, backend production
- QA status
- Known issues
- Privacy status
- IAP/subscription status
- Backend migration or compatibility status
- Rollback or mitigation plan

## Pre-checks

Before any release action:

- Run [release-check.md](../templates/codex/release-check.md).
- Use [ios-release-checklist.md](../templates/checklists/ios-release-checklist.md) for iOS release builds.
- Use [testflight-checklist.md](../templates/checklists/testflight-checklist.md) before TestFlight.
- Use [app-store-checklist.md](../templates/checklists/app-store-checklist.md) before App Store review.
- Use [privacy-checklist.md](../templates/checklists/privacy-checklist.md) before public release or privacy-sensitive changes.
- Use [iap-checklist.md](../templates/checklists/iap-checklist.md) when paid features are involved.
- Treat missing evidence as risk or blocker.

## Checklist

### 1. Scope Freeze

- [ ] Release version/build is known.
- [ ] Included changes are listed.
- [ ] Excluded changes are listed.
- [ ] Known issues are documented.
- [ ] Required fixes before submission are identified.

### 2. iOS Release Readiness

- [ ] Release build configuration is confirmed.
- [ ] Bundle ID is correct.
- [ ] Version/build number is correct.
- [ ] Signing, entitlements, and capabilities are reviewed.
- [ ] Localhost, Debug config, mock data, secrets, and API endpoint are checked.
- [ ] Crash risk and device testing are reviewed.
- [ ] watchOS companion, widgets, extensions, or companion targets are reviewed if applicable.

### 3. TestFlight Readiness

- [ ] Archive path is known.
- [ ] Upload path is known.
- [ ] Processing expectations are documented.
- [ ] Internal testing plan is ready.
- [ ] External testing and Beta App Review needs are known.
- [ ] Tester groups are identified.
- [ ] Test instructions and feedback flow are ready.
- [ ] Known issues are tester-facing.

### 4. App Store Readiness

- [ ] App name, subtitle, description, and keywords are reviewed.
- [ ] Screenshots and app preview are current.
- [ ] Support URL, Privacy Policy URL, and Terms URL are reviewed.
- [ ] Review notes and demo account are ready.
- [ ] Login requirement and age rating are reviewed.
- [ ] UGC, push notification, health/medical, financial, and effectiveness claims are reviewed.

### 5. Privacy Readiness

- [ ] Privacy Policy URL works.
- [ ] App Privacy answers match implementation.
- [ ] Data types, analytics, crash logs, user identifiers, location, health data, contact info, tracking, and third-party SDKs are reviewed.
- [ ] Account deletion is reviewed if accounts exist.

### 6. IAP / Subscription Readiness

- [ ] Product ID, reference name, subscription group, pricing, and localization are reviewed.
- [ ] Review screenshot is ready.
- [ ] Restore Purchases works.
- [ ] Terms and Privacy links are present.
- [ ] Sandbox tester and sandbox flow are ready.
- [ ] Receipt/entitlement handling and fallback behavior are reviewed.

### 7. Backend / Migration Readiness

- [ ] Backend compatibility is reviewed.
- [ ] API versioning or feature flags are documented.
- [ ] Migration plan is documented if needed.
- [ ] Rollback strategy is documented.
- [ ] Production data mutation requires explicit human confirmation.

## Safety rules

Codex must not perform these actions without explicit human confirmation:

- GitHub push, tag, or release creation
- Build upload
- TestFlight submission or tester changes
- App Store submission
- App Store Connect metadata, privacy, pricing, IAP, signing, provisioning, or availability changes
- Backend deployment
- Production database writes or migrations
- External API sends, emails, notifications, or webhooks
- Public announcements

When a real operation is needed, document only:

- target command / endpoint / screen
- payload or operation details
- impact scope
- rollback plan

## Output format

Use this release decision format:

```md
## Release Status

GO / GO WITH RISKS / NO-GO

## Scope

## Blockers

## Non-Blocking Risks

## Checks Completed

## Checks Not Completed

## Actions Prepared But Not Run

## Human Confirmation Needed

## Rollback / Mitigation
```

## Done criteria

Release readiness is done only when:

- Scope, version/build, target channel, and rollback plan are clear.
- iOS release, TestFlight, App Store, privacy, IAP, backend, migration, and known issue risks are checked where relevant.
- Blockers and non-blocking risks are separated.
- GO / GO WITH RISKS / NO-GO is stated with evidence.
- Real release operations are documented but not executed by Codex.

## Common blockers

- Version/build number conflict
- Release build or signing not confirmed
- Localhost, Debug config, mock data, secrets, or wrong API endpoint present
- Privacy Policy URL missing
- App Privacy answers do not match implementation
- TestFlight tester instructions or Beta App Review notes missing
- App Store review notes or demo account missing
- IAP products, pricing, restore purchases, or entitlement behavior unclear
- Backend migration or rollback plan missing
- Known crash or critical bug unresolved
