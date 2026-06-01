# Codex Template: App Store Review

Copy the prompt below into Codex before preparing an App Store review submission. This is a readiness review only; do not perform App Store Connect operations from this prompt.

```md
# App Store Review Readiness Prompt

## Purpose

Review an iOS app for App Store submission readiness, metadata completeness, policy risk, privacy accuracy, IAP/subscription risk, and reviewer-facing notes.

## When to use

Use this before:

- Submitting a build for App Store review
- Preparing App Store Connect metadata
- Updating screenshots, app previews, or release notes
- Adding IAP, subscriptions, login, account deletion, UGC, health, financial, or tracking behavior
- Asking a human to approve final submission

## Required inputs

App name:

Bundle ID:

Version/build:

Target release:

App category:

Support URL:

Privacy Policy URL:

Terms URL:

Login required:
- [yes/no]

Demo account:
- username:
- password or access method:
- special instructions:

IAP/subscription:
- [none / consumable / non-consumable / subscription / unknown]

Known sensitive areas:
- [health/medical / financial / UGC / tracking / push notifications / location / children / other]

Files or docs to inspect:
- 

## Pre-checks

Before giving a readiness recommendation:

- Inspect app metadata docs, release notes, privacy docs, IAP docs, and relevant app configuration if present.
- Check whether app name, subtitle, description, keywords, screenshots, app preview, support URL, privacy policy URL, terms URL, review notes, demo account, age rating, and category are accounted for.
- Check whether login requirement is justified and account deletion is available when accounts exist.
- Check whether data collection, tracking, analytics, crash logs, location, health data, contact info, third-party SDKs, and user identifiers are reflected in privacy answers.
- Check whether health/medical claims, financial claims, effectiveness claims, UGC, push notifications, and IAP/subscriptions create policy risk.
- Treat missing evidence as `unknown` or `blocker`, not as ready.

## Checklist

Review these items:

- App name is final and matches the product.
- Subtitle is accurate and not misleading.
- Description reflects current functionality.
- Keywords are relevant and policy-safe.
- Screenshots match current UI and contain no private data.
- App preview, if used, matches current app behavior.
- Support URL works and points to a real support surface.
- Privacy Policy URL works and matches implementation.
- Terms URL works when accounts, subscriptions, IAP, UGC, or legal terms are relevant.
- Review notes explain anything reviewers need to test.
- Demo account is available if login is required.
- Login requirement is justified by app functionality.
- Age rating matches content and features.
- Data collection and tracking are disclosed accurately.
- Health/medical claims are conservative and reviewed.
- Financial claims are conservative and reviewed.
- UGC has moderation, reporting, blocking, and abuse handling if applicable.
- Push notification purpose is clear and permission copy is appropriate.
- IAP/subscription copy, restore purchases, pricing, and entitlement behavior are clear.

## Safety rules

Do not perform these actions:

- Upload a build
- Submit to App Store review
- Change App Store Connect metadata
- Change pricing, IAP, subscription, or availability settings
- Add or remove testers
- Push to GitHub
- Create a release
- Send external API requests
- Modify production data

If an App Store Connect action is needed, document it only and present:

- target command / endpoint / screen
- payload or operation details
- impact scope
- rollback plan

## Output format

Return exactly these sections:

## Readiness Status

Use one:
- READY
- READY WITH RISKS
- NOT READY

## Metadata Review

## Screenshots / App Preview

## URLs / Review Notes / Demo Account

## Login / Age Rating / Account Deletion

## Privacy / Data Collection / Tracking

## Health / Medical / Financial / UGC / Push Risk

## IAP / Subscription Risk

## Common Blockers Found

## Required Fixes

## Recommended Improvements

## App Store Connect Actions Prepared But Not Run

For each action include:
- target command / endpoint / screen
- payload or operation details
- impact scope
- rollback plan

## Human Confirmation Needed

## Done criteria

This review is done only when:

- App metadata, screenshots/app preview, URLs, review notes, demo account, login, age rating, privacy, tracking, claims, UGC, push, and IAP/subscription risk have been checked.
- Blockers and non-blocking risks are separated.
- Any App Store Connect action is documented but not executed.
- The final readiness status is stated with evidence.

## Common blockers

- Missing or broken Privacy Policy URL
- Login required without demo account or reviewer instructions
- Account deletion missing for account-based apps
- Privacy answers do not match analytics, crash logs, tracking, location, or identifiers
- Screenshots or previews show outdated UI or private data
- IAP/subscription terms, pricing, restore purchases, or entitlement behavior are unclear
- Health, medical, financial, or effectiveness claims lack review
- UGC lacks moderation, reporting, or blocking
```
