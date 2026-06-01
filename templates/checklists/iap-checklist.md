# IAP Checklist

Use this checklist before releasing in-app purchases, subscriptions, paywalls, or entitlement logic.

## Purpose

Confirm that IAP/subscription configuration, pricing, localization, review screenshot, restore purchases, terms/privacy links, sandbox testing, receipt/entitlement handling, and fallback behavior are ready for review.

## When to use

Use before:

- Adding a new IAP product
- Changing pricing
- Releasing subscriptions
- Updating paywall copy
- Submitting App Store review for paid features
- Testing StoreKit, sandbox purchases, restore purchases, or entitlement behavior

## Required inputs

- [ ] Product ID:
- [ ] Reference name:
- [ ] Product type:
- [ ] Subscription group:
- [ ] Pricing:
- [ ] Localization:
- [ ] Review screenshot:
- [ ] Terms URL:
- [ ] Privacy Policy URL:
- [ ] Sandbox tester:
- [ ] Receipt/entitlement handling:
- [ ] Fallback behavior:

## Pre-checks

- [ ] Product ID and reference name are known.
- [ ] App Store Connect product status is known.
- [ ] Paywall copy is available.
- [ ] Restore Purchases entry point is available.
- [ ] Sandbox tester plan is documented.
- [ ] No App Store Connect IAP changes are executed by Codex.

## Checklist

### Product Configuration

- [ ] Product ID is final and matches app code.
- [ ] Reference name is clear.
- [ ] Product type is correct.
- [ ] Subscription group is correct if applicable.
- [ ] Pricing is reviewed.
- [ ] Localization is reviewed.
- [ ] Review screenshot is prepared.
- [ ] Product status and review requirements are understood.

### App Behavior

- [ ] Paywall copy is accurate.
- [ ] Purchase flow is tested.
- [ ] Restore Purchases works.
- [ ] Entitlement state updates correctly.
- [ ] Receipt or transaction handling is implemented.
- [ ] Fallback behavior works when purchase, network, or receipt validation fails.
- [ ] Cancellation, expiration, grace period, and billing retry behavior are considered for subscriptions.

### Policy And Links

- [ ] Terms URL is present where required.
- [ ] Privacy Policy URL is present.
- [ ] Subscription terms are visible.
- [ ] Pricing and renewal copy are not misleading.
- [ ] External payment links are policy-safe.

### Sandbox And Backend

- [ ] Sandbox tester is available.
- [ ] StoreKit configuration or sandbox test path is documented.
- [ ] Backend receipt validation is reviewed if used.
- [ ] Server notifications are reviewed if used.
- [ ] Entitlement rollback or manual support path is documented.

## Safety rules

- [ ] Do not change App Store Connect IAP products from Codex.
- [ ] Do not change pricing from Codex.
- [ ] Do not submit IAP products for review from Codex.
- [ ] Do not send external API requests or modify production entitlement data from Codex.

If action is needed, document:

- target command / endpoint / screen
- payload or operation details
- impact scope
- rollback plan

## Output format

Record review results as:

```md
## IAP Status

READY / READY WITH RISKS / NOT READY

## Product Configuration

## App Behavior

## Terms / Privacy / Policy Risks

## Sandbox / Receipt / Entitlement Risks

## Required Fixes

## Human Confirmation Needed
```

## Done criteria

- [ ] Product ID, reference name, subscription group, pricing, localization, review screenshot, Restore Purchases, Terms/Privacy links, sandbox tester, receipt/entitlement handling, and fallback behavior are checked.
- [ ] Product configuration and app behavior are consistent.
- [ ] Blockers and non-blocking risks are separated.
- [ ] App Store Connect actions are documented but not executed.

## Common blockers

- [ ] Product ID in code does not match App Store Connect
- [ ] Subscription group or pricing unclear
- [ ] Review screenshot missing
- [ ] Restore Purchases missing or broken
- [ ] Terms or Privacy link missing
- [ ] Sandbox purchase path not tested
- [ ] Receipt/entitlement handling unclear
- [ ] Fallback behavior missing
