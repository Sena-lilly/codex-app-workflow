# Initial Issue Drafts

Use these drafts after the repository is public. Do not create GitHub issues automatically; copy them manually after human review.

Repository:

- `https://github.com/Sena-lilly/codex-app-workflow`

## Issue 1

Title:

```text
Add side-effect operation examples
```

Why:

- The safety standards are central to this project, but concrete examples will make them easier for first-time users to apply.
- Users should see how to ask Codex to prepare, but not execute, high-risk operations.

Scope:

- Add examples for GitHub push, release creation, external API send, production database write, App Store submission, TestFlight operation, and billing/pricing changes.
- Keep examples fictional and free of credentials, private project names, or production data.
- Show the required pre-confirmation format: target, payload or operation details, impact scope, and rollback plan.

Expected files:

- `docs/safety-standards.md`
- `templates/checklists/safety-checklist.md`
- `examples/session-handoff-example.md` or a new example file if needed

Acceptance criteria:

- At least five side-effect operation examples are documented.
- Each example clearly states that Codex must not execute the operation without explicit human confirmation.
- Each example includes target, payload or operation details, impact scope, and rollback plan.
- No real secrets, account identifiers, customer data, URLs for private systems, or internal project details are included.

Labels:

- `documentation`
- `safety`
- `good first issue`

## Issue 2

Title:

```text
Improve README quickstart for first-time Codex users
```

Why:

- The README should help people who are new to Codex understand what to copy first and how to avoid unsafe workflows.
- Early feedback may reveal unclear wording in Start Here, Workflow At A Glance, or Examples.

Scope:

- Review the first viewport of `README.md`.
- Improve the path from README to `docs/quickstart-paths.md`.
- Clarify which template to copy first for audit, implementation, bug investigation, TestFlight, and App Store review.
- Keep the README concise.

Expected files:

- `README.md`
- `docs/quickstart-paths.md`

Acceptance criteria:

- A first-time Codex user can identify the first template to copy within 30 seconds.
- The README links clearly to quickstart paths and examples.
- The wording does not overpromise automation, safety, or release readiness.
- Markdown relative links still resolve.

Labels:

- `documentation`
- `beginner-friendly`
- `good first issue`

## Issue 3

Title:

```text
Add Fastlane and Xcode Cloud workflow templates
```

Why:

- iOS developers often use Fastlane or Xcode Cloud for release automation, screenshots, metadata, signing, and TestFlight workflows.
- These workflows can involve App Store Connect, credentials, signing, and release side effects, so they need clear human-confirmation boundaries.

Scope:

- Add Codex templates for auditing Fastlane and Xcode Cloud workflows.
- Include dry-run guidance, secret checks, signing/capabilities checks, release gating, and rollback notes.
- Do not include real Fastlane credentials, App Store Connect API keys, Apple Developer details, or private app metadata.

Expected files:

- `templates/codex/fastlane-workflow-check.md`
- `templates/codex/xcode-cloud-workflow-check.md`
- `templates/checklists/ios-release-checklist.md`
- `docs/release-management.md`

Acceptance criteria:

- Fastlane and Xcode Cloud templates include Purpose, When to use, Inputs, Constraints, Safety rules, Required checks, Output format, and Done criteria.
- Templates explicitly forbid executing uploads, submissions, signing changes, or App Store Connect changes without human confirmation.
- Required confirmation format includes target, payload or operation details, impact scope, and rollback plan.
- Examples use placeholders only.

Labels:

- `ios`
- `release`
- `templates`

## Issue 4

Title:

```text
Add real-world case study using this workflow
```

Why:

- The project will be easier to evaluate if users can see how the workflow behaves across a realistic development session.
- A case study can show where thread splitting, handoff, safety checks, and release review help in practice.

Scope:

- Add one fictionalized or anonymized case study.
- Cover initial audit, one implementation or bugfix, verification, handoff, and release/safety considerations.
- Avoid private project names, personal data, customer data, screenshots, credentials, and unreleased product strategy.

Expected files:

- `examples/real-world-case-study-example.md`
- `docs/security-audit-log.md` if a privacy/sensitive-information audit is performed for the example
- `README.md` if the new example should be linked

Acceptance criteria:

- The case study is realistic but does not disclose private information.
- It shows the starting prompt, expected Codex workflow, expected output, and handoff.
- It includes at least one safety or human-confirmation checkpoint.
- It states known limitations and what was intentionally left out.

Labels:

- `examples`
- `documentation`
- `case-study`

