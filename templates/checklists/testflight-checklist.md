# TestFlight Checklist

Use this checklist before asking a human to upload a build, start internal testing, start external testing, or submit Beta App Review.

## Purpose

Confirm that a TestFlight rollout is ready across archive, upload, processing, tester groups, test instructions, known issues, feedback flow, and App Store Connect approval gates.

## When to use

Use before:

- Creating an archive for testers
- Uploading a build
- Waiting for or checking build processing
- Starting internal testing
- Starting external testing
- Submitting Beta App Review
- Adding tester groups or sending instructions

## Required inputs

- [ ] App name:
- [ ] Bundle ID:
- [ ] Version/build:
- [ ] Tester group:
- [ ] Testing goal:
- [ ] Archive method:
- [ ] Upload method:
- [ ] Known issues:
- [ ] Feedback channel:

## Pre-checks

- [ ] Release build configuration is identified.
- [ ] Version/build number is unique.
- [ ] Target backend/API environment is known.
- [ ] Tester instructions are drafted.
- [ ] Known issues are written in tester-facing language.
- [ ] No TestFlight or App Store Connect actions are executed by Codex.

## Checklist

### Archive / Upload / Processing

- [ ] Archive method is known.
- [ ] Upload method is known.
- [ ] Build processing expectations are documented.
- [ ] Signing/provisioning status is known.
- [ ] Bundle ID is correct.
- [ ] Version/build number is correct.
- [ ] Release notes for testers are ready.

### Internal Testing

- [ ] Internal tester group is selected.
- [ ] Internal test goal is documented.
- [ ] Smoke test instructions are ready.
- [ ] Feedback flow is ready.

### External Testing / Beta App Review

- [ ] External tester group is selected if needed.
- [ ] Beta App Review notes are prepared if external testing is needed.
- [ ] Demo account is available if login is required.
- [ ] Export compliance or encryption status is known if relevant.
- [ ] Public-facing tester instructions are clear.

### Test Safety

- [ ] Known issues are documented.
- [ ] API endpoint is correct for testing.
- [ ] Debug UI, mock data, verbose logs, localhost URLs, and secrets are checked.
- [ ] Test accounts do not expose real user data.
- [ ] IAP sandbox tester instructions are ready if IAP/subscriptions are involved.
- [ ] Privacy-sensitive flows are reviewed.

## Safety rules

- [ ] Do not upload builds from Codex.
- [ ] Do not add testers from Codex.
- [ ] Do not start internal or external testing from Codex.
- [ ] Do not submit Beta App Review from Codex.
- [ ] Do not change App Store Connect settings from Codex.
- [ ] Do not send external API requests or modify production data.

If action is needed, document:

- target command / endpoint / screen
- payload or operation details
- impact scope
- rollback plan

## Output format

Record review results as:

```md
## TestFlight Status

READY / READY WITH RISKS / NOT READY

## Blockers

## Non-Blocking Risks

## Tester Instructions

## Known Issues

## TestFlight Actions Prepared But Not Run

## Human Confirmation Needed
```

## Done criteria

- [ ] Archive, upload, processing, internal testing, external testing, Beta App Review, tester groups, instructions, known issues, and feedback flow are checked.
- [ ] Environment, debug, localhost, secrets, login, privacy, and IAP risks are reviewed.
- [ ] TestFlight actions are documented but not executed.
- [ ] Human owner has enough information to approve or delay testing.

## Common blockers

- [ ] Version/build number conflict
- [ ] Release build configuration not confirmed
- [ ] Wrong API endpoint or localhost URL
- [ ] Debug UI, mock data, verbose logs, or secrets present
- [ ] External testing needs Beta App Review notes
- [ ] Tester group or feedback flow missing
- [ ] Known issues not documented
