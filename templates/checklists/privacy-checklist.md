# Privacy Checklist

Use this checklist before release when the app collects, stores, processes, tracks, analyzes, shares, or displays user data.

## Purpose

Confirm that privacy policy, App Privacy answers, data types, analytics, crash logs, user identifiers, location, health data, contact info, tracking, and third-party SDKs match actual app behavior.

## When to use

Use before:

- App Store submission
- TestFlight external testing
- Adding analytics, crash reporting, ads, tracking, location, health data, contact info, or account features
- Updating App Privacy answers
- Adding third-party SDKs
- Public release

## Required inputs

- [ ] Privacy Policy URL:
- [ ] Data collected:
- [ ] Data linked to user:
- [ ] Data used for tracking:
- [ ] Third-party SDKs:
- [ ] Analytics provider:
- [ ] Crash reporting provider:
- [ ] Account deletion path:
- [ ] Regions or age groups affected:

## Pre-checks

- [ ] Data inventory is available.
- [ ] Privacy Policy URL is accessible.
- [ ] App Privacy answers are available or can be drafted.
- [ ] Third-party SDK list is known.
- [ ] No production data or private user data is exposed during review.

## Checklist

### Data Types

- [ ] Contact info is reviewed.
- [ ] User identifiers are reviewed.
- [ ] Device identifiers are reviewed.
- [ ] Usage data is reviewed.
- [ ] Diagnostics and crash logs are reviewed.
- [ ] Location data is reviewed.
- [ ] Health data is reviewed.
- [ ] Financial info is reviewed if applicable.
- [ ] User content is reviewed if applicable.

### Collection, Use, And Sharing

- [ ] Purpose of collection is documented.
- [ ] Data linked to user is identified.
- [ ] Data not linked to user is identified.
- [ ] Tracking behavior is identified.
- [ ] Analytics behavior is disclosed.
- [ ] Crash log behavior is disclosed.
- [ ] Third-party SDK data collection is reviewed.
- [ ] Data retention expectations are documented.
- [ ] Account deletion flow is available if accounts exist.

### User-Facing Privacy

- [ ] Privacy Policy URL works.
- [ ] App Privacy answers match implementation.
- [ ] Permission prompts are accurate.
- [ ] Consent or opt-out behavior is reviewed if relevant.
- [ ] Sensitive data is not logged or shown in debug output.

## Safety rules

- [ ] Do not send data to external services from Codex.
- [ ] Do not modify production data.
- [ ] Do not change App Store Connect privacy answers from Codex.
- [ ] Do not expose real user data, private emails, tokens, or production URLs in notes.

If action is needed, document:

- target command / endpoint / screen
- payload or operation details
- impact scope
- rollback plan

## Output format

Record review results as:

```md
## Privacy Status

READY / READY WITH RISKS / NOT READY

## Data Types Reviewed

## App Privacy Answer Risks

## Third-Party SDK Risks

## Required Fixes

## Human Confirmation Needed
```

## Done criteria

- [ ] Privacy Policy URL, App Privacy answers, data types, analytics, crash logs, user identifiers, location, health data, contact info, tracking, and third-party SDKs are checked.
- [ ] Mismatches between implementation and disclosure are identified.
- [ ] Blockers and non-blocking risks are separated.
- [ ] Any App Store Connect privacy action is documented but not executed.

## Common blockers

- [ ] Privacy Policy URL missing or broken
- [ ] App Privacy answers do not match SDK behavior
- [ ] Tracking not disclosed
- [ ] User identifiers or contact info not disclosed
- [ ] Location or health data unclear
- [ ] Account deletion missing for account-based apps
- [ ] Sensitive data appears in logs or test data
