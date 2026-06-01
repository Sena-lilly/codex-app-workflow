# Codex Template: TestFlight Preparation

Copy the prompt below into Codex before preparing a TestFlight build or tester rollout. This is a readiness review only; do not upload builds or change App Store Connect.

```md
# TestFlight Preparation Prompt

## Purpose

Prepare a TestFlight rollout plan by checking archive readiness, upload requirements, processing expectations, tester groups, beta review needs, instructions, known issues, and feedback flow.

## When to use

Use this before:

- Archiving an iOS release build
- Uploading a build to App Store Connect
- Starting internal testing
- Starting external testing
- Submitting Beta App Review
- Adding tester groups
- Sending tester instructions

## Required inputs

App name:

Bundle ID:

Version/build:

Target tester group:
- [internal / external / named group]

Testing goal:

Archive method:
- [Xcode / xcodebuild / Fastlane / Xcode Cloud / unknown]

Upload method:
- [Xcode Organizer / Transporter / Fastlane / Xcode Cloud / unknown]

Known issues:
- 

Feedback flow:
- [email / TestFlight feedback / issue tracker / form / other]

Files or docs to inspect:
- 

## Pre-checks

Before giving a readiness recommendation:

- Inspect version/build, release config, signing notes, release notes, tester instructions, known issues, and feedback docs if present.
- Check archive, upload, processing, internal testing, external testing, Beta App Review, tester groups, test instructions, known issues, and feedback flow.
- Check whether the build points to the correct API endpoint and environment.
- Check whether debug-only UI, localhost URLs, secrets, mock data, verbose logging, and feature flags are acceptable.
- Check whether IAP sandbox behavior, login accounts, privacy-sensitive flows, and backend compatibility are ready for testers.
- Treat missing evidence as `unknown` or `blocker`.

## Checklist

Review these items:

- Archive method is known.
- Release build configuration is selected.
- Version/build number is correct and unique.
- Bundle ID is correct.
- Signing/provisioning status is known.
- Upload method is known.
- Build processing expectations are documented.
- Internal tester group is identified.
- External tester group is identified if needed.
- Beta App Review requirements are identified for external testing.
- Tester instructions explain what to test.
- Known issues are documented in tester-facing language.
- Feedback flow is ready.
- Test accounts are available if login is required.
- IAP sandbox testing instructions exist if IAP/subscriptions are involved.
- API endpoint is correct for the test channel.
- Debug, localhost, mock, and secret risks are checked.

## Safety rules

Do not perform these actions:

- Archive or upload a build unless explicitly requested and safe locally
- Upload to App Store Connect
- Add testers
- Start internal testing
- Start external testing
- Submit Beta App Review
- Change App Store Connect settings
- Push to GitHub
- Create a release
- Send external API requests
- Modify production data

If a TestFlight or App Store Connect action is needed, document it only and present:

- target command / endpoint / screen
- payload or operation details
- impact scope
- rollback plan

## Output format

Return exactly these sections:

## TestFlight Readiness Status

Use one:
- READY
- READY WITH RISKS
- NOT READY

## Archive / Upload / Processing

## Internal Testing

## External Testing / Beta App Review

## Tester Groups

## Test Instructions

## Known Issues

## Feedback Flow

## Environment / Debug / Secrets

## IAP / Login / Privacy Notes

## Common Blockers Found

## Required Fixes

## TestFlight Actions Prepared But Not Run

For each action include:
- target command / endpoint / screen
- payload or operation details
- impact scope
- rollback plan

## Human Confirmation Needed

## Done criteria

This preparation is done only when:

- Archive, upload, processing, internal testing, external testing, Beta App Review, tester groups, instructions, known issues, and feedback flow are checked.
- Environment, debug, localhost, secrets, login, privacy, and IAP risks are reviewed.
- Required TestFlight actions are documented but not executed.
- Readiness status is stated with evidence.

## Common blockers

- Version/build number already used or unknown
- Release build configuration not confirmed
- Build points to localhost or wrong backend environment
- Debug UI, mock data, verbose logs, or secrets are present
- External testing needs Beta App Review but notes are missing
- Tester groups or instructions are unclear
- Known issues are not documented
- Feedback flow is missing
```
