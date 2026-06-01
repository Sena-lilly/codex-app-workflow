# iOS Release Checklist

Use this checklist before preparing an iOS release build, archive, TestFlight rollout, or App Store submission.

## Purpose

Confirm that the iOS app is release-ready across build settings, signing, capabilities, environment config, secrets, API endpoints, crash risk, device testing, and companion targets.

## When to use

Use before:

- Release build
- Archive
- TestFlight upload
- App Store submission
- Version/build change
- Signing, entitlement, capability, or API endpoint change

## Required inputs

- [ ] App target:
- [ ] Scheme:
- [ ] Bundle ID:
- [ ] Version/build:
- [ ] Release channel:
- [ ] API endpoint:
- [ ] Signing team/profile:
- [ ] Device test scope:
- [ ] Companion targets, if any:

## Pre-checks

- [ ] Release build configuration is known.
- [ ] Version/build number source is known.
- [ ] Bundle ID is confirmed.
- [ ] Signing/provisioning owner is known.
- [ ] No App Store Connect or TestFlight operations are executed by Codex.

## Checklist

### Build And Project Configuration

- [ ] Release build configuration is selected.
- [ ] Version number is correct.
- [ ] Build number is correct and unique.
- [ ] Bundle ID is correct.
- [ ] Deployment target is intentional.
- [ ] App icons are present.
- [ ] Launch screen works.
- [ ] Signing configuration is reviewed.
- [ ] Entitlements are reviewed.
- [ ] Capabilities are reviewed.
- [ ] Extensions, widgets, and watchOS companion targets are reviewed if applicable.

### Environment And Secrets

- [ ] API endpoint is correct for release.
- [ ] No localhost or `127.0.0.1` URLs remain in release config.
- [ ] Debug flags and debug menus are disabled or intentionally gated.
- [ ] Mock data and test endpoints are removed or intentionally gated.
- [ ] Secrets, API keys, tokens, `.env`, signing files, and production credentials are not committed.
- [ ] Push notification environment is correct if used.

### App Behavior And Risk

- [ ] App launches successfully.
- [ ] Main user flows pass smoke testing.
- [ ] Device testing completed on representative devices.
- [ ] Simulator-only assumptions are removed.
- [ ] Crash risk and crash reporting are reviewed.
- [ ] Offline or poor-network behavior is acceptable.
- [ ] Error states are user-friendly.
- [ ] Accessibility basics are reviewed.
- [ ] Localization is reviewed if used.
- [ ] IAP/subscription behavior is tested if used.

## Safety rules

- [ ] Do not upload builds from Codex.
- [ ] Do not submit to TestFlight or App Store from Codex.
- [ ] Do not change signing, provisioning, capabilities, or App Store Connect settings without explicit human confirmation.
- [ ] Do not send external API requests or modify production data.

If action is needed, document:

- target command / endpoint / screen
- payload or operation details
- impact scope
- rollback plan

## Output format

Record review results as:

```md
## iOS Release Status

READY / READY WITH RISKS / NOT READY

## Blockers

## Non-Blocking Risks

## Checks Completed

## Checks Not Completed

## Human Confirmation Needed
```

## Done criteria

- [ ] Release build, version/build number, Bundle ID, signing, entitlements, capabilities, localhost/Debug config, secrets, API endpoint, crash risk, device testing, and watchOS companion if applicable are checked.
- [ ] Blockers and non-blocking risks are separated.
- [ ] Upload/submission actions are documented but not executed.
- [ ] Human owner has enough information to approve archive/upload/submission.

## Common blockers

- [ ] Wrong Bundle ID
- [ ] Signing/provisioning mismatch
- [ ] Entitlement or capability mismatch
- [ ] Localhost or Debug config in release build
- [ ] Secrets or production credentials committed
- [ ] Wrong API endpoint
- [ ] Crash on launch or untested critical flow
- [ ] Companion target not reviewed
