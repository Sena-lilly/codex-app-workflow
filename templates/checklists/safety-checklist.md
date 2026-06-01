# Safety Checklist

Use before running risky commands, release operations, or workflows that affect users or external systems.

## Operation Type

- [ ] This is local-only and safe to run.
- [ ] This may create, update, or delete real data or settings.
- [ ] This may approve or reject a real request, review, purchase, account, release, or policy state.
- [ ] This may contact an external service.
- [ ] This may modify production data.
- [ ] This may send, publish, release, deploy, upload, or submit something.
- [ ] This may change billing, subscriptions, or IAP.
- [ ] This may publish code, tags, builds, or releases.
- [ ] This may notify real users.
- [ ] This may destroy or overwrite data.

## Required Information

- [ ] Target command, endpoint, screen, service, file, or resource is documented.
- [ ] Payload or operation details are documented.
- [ ] Impact scope is documented.
- [ ] Rollback plan is documented.
- [ ] Recovery path is documented.
- [ ] Revert method is documented.
- [ ] Known rollback limitations are documented.
- [ ] Owner approval is documented.

## Mutation Safety Standard

- [ ] The operation has been classified as read-only, local-only, or mutation-sensitive.
- [ ] Create/update/delete behavior has been identified.
- [ ] Approve/reject behavior has been identified.
- [ ] Send/publish/release/deploy/upload/submit behavior has been identified.
- [ ] Production data, external systems, billing, IAP, App Store, TestFlight, GitHub, and deployment impact have been considered.
- [ ] Readiness review is separated from execution.

## Rollback Standard

- [ ] Rollback plan is specific.
- [ ] Recovery path returns the project to a known-safe state.
- [ ] Revert method is actionable.
- [ ] Known limitations are explicit.
- [ ] Dry-run, staging check, backup, feature flag, or kill switch has been considered.
- [ ] If rollback is unknown or partial, the risk is escalated to the human owner before execution.

## Safer Alternatives

- [ ] Dry-run is available or considered.
- [ ] Local test is available or considered.
- [ ] Staging environment is available or considered.
- [ ] Backup exists, if data could be changed.
- [ ] Feature flag or kill switch exists, if relevant.

## Sensitive Information Audit

Treat personal information, confidential information, secrets, and production settings as high-risk release blockers.

- [ ] A heavy repository-wide sensitive information audit has been completed.
- [ ] The audit checked more than simple grep results.
- [ ] Suspicious strings, filenames, configuration files, sample data, docs, and templates were reviewed.
- [ ] API keys, tokens, secrets, passwords, `.env` files, Firebase plist files, Apple Developer information, and App Store Connect information were checked.
- [ ] Private emails, personal names, phone numbers, addresses, customer data, production URLs, and production database URLs were checked.
- [ ] Internal project information, company confidential information, and unpublished product strategy were checked.
- [ ] Any real sensitive values were removed or replaced with sample placeholders.
- [ ] Findings and actions were recorded in `docs/security-audit-log.md` or `progress.md`.
- [ ] The audit is required before public release, before release operations, and after large changes.
- [ ] Deep review is prioritized over speed, even if Codex usage increases.

## Confirmation Gate

Do not proceed until the human explicitly confirms the exact operation.

Confirmation prompt:

```md
Human confirmation required.

Target:
[command / endpoint / screen / resource]

Payload / operation details:
[payload, settings, metadata, or manual change]

Impact scope:
[users, data, environments, releases, billing, repositories, or external systems affected]

Rollback:
- rollback plan:
- recovery path:
- revert method:
- known limitations:

Please confirm before I proceed.
```
