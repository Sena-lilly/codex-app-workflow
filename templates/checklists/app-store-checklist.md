# App Store Checklist

Use this checklist before asking a human to submit an app for App Store review. Do not use it to perform App Store Connect operations automatically.

## Purpose

Confirm that App Store metadata, review notes, privacy disclosures, IAP/subscriptions, screenshots, app preview, URLs, and policy-sensitive areas are ready for human approval.

## When to use

Use before:

- App Store review submission
- Metadata updates
- Screenshot or app preview updates
- IAP/subscription release
- Adding login, UGC, tracking, push notifications, health/medical, or financial features

## Required inputs

- [ ] App name:
- [ ] Bundle ID:
- [ ] Version/build:
- [ ] Category:
- [ ] Support URL:
- [ ] Privacy Policy URL:
- [ ] Terms URL:
- [ ] Demo account or reviewer access:
- [ ] IAP/subscription status:
- [ ] Known sensitive areas:

## Pre-checks

- [ ] App Store Connect metadata has been reviewed manually or from exported notes.
- [ ] Current app behavior matches submitted metadata.
- [ ] Required URLs are accessible.
- [ ] Privacy and IAP checklists have been reviewed if applicable.
- [ ] No App Store Connect changes are executed by Codex.

## Checklist

### Metadata

- [ ] App name is final.
- [ ] Subtitle is accurate.
- [ ] Description matches current functionality.
- [ ] Keywords are relevant and not misleading.
- [ ] Category is correct.
- [ ] Age rating matches app content and capabilities.
- [ ] Release notes are clear and user-facing.

### Media

- [ ] Screenshots match current UI.
- [ ] Screenshots cover required device sizes.
- [ ] Screenshots show no private data.
- [ ] App preview, if used, matches current behavior.
- [ ] App preview shows no private data or unsupported claims.

### URLs And Reviewer Access

- [ ] Support URL works.
- [ ] Privacy Policy URL works.
- [ ] Terms URL works when accounts, IAP, subscriptions, UGC, or legal terms are relevant.
- [ ] Review notes explain special setup, limitations, or hardware requirements.
- [ ] Demo account is provided if login is required.
- [ ] Login requirement is justified by app functionality.
- [ ] Account deletion is available if accounts exist.

### Policy Risk

- [ ] Data collection and tracking disclosures match implementation.
- [ ] Push notification purpose is clear.
- [ ] UGC moderation, reporting, blocking, and abuse handling are documented if applicable.
- [ ] Health/medical claims are reviewed.
- [ ] Financial claims are reviewed.
- [ ] Legal, safety, or effectiveness claims are reviewed.
- [ ] External links and payment flows are policy-safe.
- [ ] IAP/subscription copy, pricing, restore purchases, and entitlement behavior are reviewed.

## Safety rules

- [ ] Do not submit to App Store review from Codex.
- [ ] Do not upload builds from Codex.
- [ ] Do not change App Store Connect metadata from Codex.
- [ ] Do not change IAP, pricing, subscription, signing, provisioning, or availability settings from Codex.
- [ ] Do not send external API requests or modify production data.

If action is needed, document:

- target command / endpoint / screen
- payload or operation details
- impact scope
- rollback plan

## Output format

Record review results as:

```md
## App Store Status

READY / READY WITH RISKS / NOT READY

## Blockers

## Non-Blocking Risks

## Required Fixes

## App Store Connect Actions Prepared But Not Run

## Human Confirmation Needed
```

## Done criteria

- [ ] App name, subtitle, description, keywords, screenshots, app preview, support URL, privacy policy URL, terms URL, review notes, demo account, login, age rating, data collection, tracking, claims, UGC, push, and IAP/subscription risk are checked.
- [ ] Blockers and non-blocking risks are separated.
- [ ] App Store Connect actions are documented but not executed.
- [ ] Human owner has enough information to decide whether to submit.

## Common blockers

- [ ] Missing or broken Privacy Policy URL
- [ ] Missing support URL
- [ ] Demo account missing when login is required
- [ ] Account deletion missing for account-based apps
- [ ] Privacy answers do not match implementation
- [ ] Screenshots or app preview are outdated
- [ ] IAP/subscription terms or restore behavior unclear
- [ ] UGC safety controls missing
- [ ] Health, medical, financial, or effectiveness claims not reviewed
