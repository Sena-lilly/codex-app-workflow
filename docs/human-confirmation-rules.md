# Human Confirmation Rules

Codex must not perform real-world side-effect operations without explicit human confirmation.

The canonical standards are defined in [safety-standards.md](safety-standards.md).

## Side-Effect Operations

The following require confirmation:

- Create operations against real systems
- Update operations against real systems
- Delete operations against real systems
- Approve or reject operations
- Send, publish, release, deploy, upload, or submit operations
- Production database writes
- Data migrations against production
- External API sends
- Emails, notifications, or webhooks to real users
- GitHub pushes
- Git tags
- GitHub release creation
- App Store submission
- TestFlight submission
- Billing, subscription, or IAP changes
- Destructive infrastructure actions
- Secret rotation
- Permission or access-control changes

## Required Confirmation Format

Before asking for approval, Codex should present:

- Target: command, endpoint, screen, service, file, or resource
- Payload: request body, operation details, settings, metadata, or manual changes
- Impact scope: users, data, environments, releases, billing, repositories, or external systems affected
- Rollback: rollback plan, recovery path, revert method, and known limitations

Example:

```md
Human confirmation required.

Target:
fastlane pilot upload

Payload / operation details:
App Store Connect app APP_BUNDLE_ID, TestFlight build train 1.2.0

Impact scope:
Uploads a new build to TestFlight for internal testing.

Rollback:
- rollback plan: Expire the build in App Store Connect or stop external distribution before adding testers.
- recovery path: Keep the previous TestFlight build available.
- revert method: Remove tester access or expire the uploaded build.
- known limitations: Uploaded build records may remain visible in App Store Connect history.
```

## Safe Without Extra Confirmation

These actions are usually safe when performed locally:

- Reading files
- Creating documentation
- Editing local templates
- Running local tests
- Running local formatters
- Performing dry-runs
- Inspecting logs that do not contain secrets

## Risky Even Locally

Ask before running commands that:

- Delete files
- Rewrite Git history
- Modify signing identities
- Change environment files with real credentials
- Run migrations without a dry-run
- Contact external services

## Confirmation Must Be Specific

General approval such as "do the release" is not enough for dangerous operations.

The confirmation should match the actual operation, target, payload, impact scope, rollback plan, recovery path, revert method, and known limitations.
