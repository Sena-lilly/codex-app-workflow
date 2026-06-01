# Security Policy

## Supported Versions

This project is in early bootstrap. Until the first stable release, security guidance applies to the `main` branch and the latest published release, if any.

## Reporting a Vulnerability

If you find a security issue in a template or workflow, please report it privately through the repository's security advisory feature when available.

If security advisories are not enabled yet, open a minimal public issue that says a private security report is needed, without disclosing exploit details.

## What Counts as a Security Issue?

Examples include:

- A template that encourages sending secrets to external services
- A release workflow that skips human confirmation for production changes
- A checklist that omits rollback planning for destructive operations
- Guidance that could expose customer data, credentials, tokens, or signing keys
- Unsafe defaults for App Store, TestFlight, backend, or billing workflows

## Handling Sensitive Data

Do not include real secrets, customer data, private bundle identifiers, signing credentials, provisioning profiles, API keys, or production URLs in issues, pull requests, examples, screenshots, or templates.

Use placeholders such as:

- `APP_BUNDLE_ID`
- `API_BASE_URL`
- `APPLE_TEAM_ID`
- `DATABASE_URL`
- `STRIPE_SECRET_KEY`

## Security Review Standard

When a workflow touches production, releases, billing, user data, or external services, it must require explicit human confirmation with:

- Target command
- Target resources
- Expected impact
- Rollback method
