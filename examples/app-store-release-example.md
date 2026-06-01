# App Store Release Example

This example shows how to use Codex for App Store release readiness without performing App Store Connect or TestFlight operations.

## Scenario

`Sample Wellness App` is preparing version `1.2.0` for App Store review. The release includes a new guided breathing session and a small onboarding copy update.

The app has no real medical diagnosis feature, but some copy mentions wellness benefits. The release also uses analytics and crash reporting.

## Goal

Review App Store readiness, privacy, metadata, screenshots, review notes, demo access, health/medical claim risk, and go/no-go status.

## Starting prompt

Paste this into a new Codex thread:

```md
Use templates/threads/release-thread-template.md, templates/codex/app-store-review.md, and templates/codex/release-check.md.

App:
Sample Wellness App

Release target:
App Store review

Version/build:
1.2.0 / [build number]

Release scope:
- Guided breathing session
- Onboarding copy update
- Minor bug fixes

Known sensitive areas:
- wellness claims
- analytics
- crash reporting

Required review:
- App Store metadata
- screenshots and app preview
- support URL
- privacy policy URL
- terms URL
- review notes
- demo account if login is required
- data collection and tracking
- health/medical claim risk

Safety:
Do not upload builds, submit to App Store, change App Store Connect, push to GitHub, create releases, contact external APIs, or modify production data.
If any App Store Connect action is needed, document target, payload, impact scope, and rollback only.
```

## Recommended template

- [Release thread template](../templates/threads/release-thread-template.md)
- [App Store review template](../templates/codex/app-store-review.md)
- [Release check template](../templates/codex/release-check.md)
- [App Store checklist](../templates/checklists/app-store-checklist.md)
- [Privacy checklist](../templates/checklists/privacy-checklist.md)

## Expected workflow

1. Confirm release target, version/build, scope, and channel.
2. Inspect release notes, metadata notes, privacy docs, screenshots notes, and review checklist.
3. Check app name, subtitle, description, keywords, screenshots, app preview, support URL, privacy policy URL, terms URL, review notes, demo access, login, and age rating.
4. Check data collection, tracking, analytics, crash logs, third-party SDKs, and user identifiers.
5. Check wellness copy for health/medical or effectiveness claim risk.
6. Classify blockers and non-blocking risks.
7. Prepare App Store Connect actions but do not execute them.
8. Produce GO / GO WITH RISKS / NO-GO.

## Expected output

```md
## Release Readiness Status

GO WITH RISKS

## Release Target / Scope / Version

Target: App Store review
Version/build: 1.2.0 / [build number]
Scope: guided breathing session, onboarding copy update, minor bug fixes

## App Store Readiness

- App name, subtitle, description, keywords: ready from provided notes
- Screenshots: needs final human visual review
- App preview: not used
- Support URL, Privacy Policy URL, Terms URL: present as placeholders pending human verification
- Review notes: should mention no medical diagnosis is provided
- Demo account: not needed if login is not required

## Privacy Readiness

- Analytics and crash reporting must match App Privacy answers.
- Tracking status must be confirmed by human owner.

## Health / Medical Claim Risk

Wellness copy should avoid diagnosis, treatment, cure, or guaranteed outcome claims.

## Blocking Issues

None found in reviewed local documentation.

## Non-Blocking Risks

- Screenshots require human visual confirmation.
- Privacy answers require final App Store Connect verification.
- Wellness copy should be reviewed by legal/human owner.

## App Store Connect Actions Prepared But Not Run

- target command / endpoint / screen: App Store Connect metadata screen
- payload or operation details: update metadata and review notes for 1.2.0
- impact scope: public App Store submission metadata
- rollback plan: edit metadata before submission or reject/remove submitted version if still possible

## Human Confirmation Needed

Final App Store submission requires explicit human confirmation.
```

## Handoff example

```md
## Goal

Review Sample Wellness App 1.2.0 for App Store readiness.

## Current State

Readiness review complete. No App Store Connect action executed.

## Completed

- Reviewed release scope.
- Reviewed App Store metadata checklist.
- Reviewed privacy and wellness claim risks.
- Prepared actions but did not run them.

## Not Completed

- Human visual screenshot review.
- Human verification of App Privacy answers in App Store Connect.
- Final submission.

## Important Decisions

- decision: Mark as GO WITH RISKS.
- reason: No local blocker found, but screenshots/privacy/wellness copy need human confirmation.
- tradeoff: Release can proceed only after owner accepts remaining risks.

## Files Changed

None in the app project.

## Commands Run

Local file inspection only.

## Checks / Verification

Metadata, privacy, claim risk, and release notes were reviewed from local docs/templates.

## Known Issues / Risks

Wellness copy must avoid medical claims.

## Human Confirmation Needed

App Store submission requires target, payload, impact scope, and rollback.

## Next Prompt

Use templates/agents/legal-review-agent.md to review wellness copy and privacy disclosures.
```

## Common mistakes

- Submitting to App Store Connect from a readiness thread.
- Treating placeholder URLs as verified live URLs.
- Missing App Privacy answers for analytics or crash reporting.
- Using medical or effectiveness claims without review.
- Forgetting review notes for app behavior that reviewers need to understand.

## Done criteria

- App Store readiness is classified as READY, READY WITH RISKS, or NOT READY.
- Privacy, metadata, screenshots, review notes, and claim risk are checked.
- App Store Connect actions are documented but not executed.
- Human confirmation requirements are explicit.
- Release handoff is ready.
