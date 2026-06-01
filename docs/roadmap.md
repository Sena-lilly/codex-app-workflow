# Roadmap

This roadmap tracks the path from bootstrap to a useful v1.0 workflow kit.

## P0: Repository Bootstrap

Goal: Create the public OSS foundation.

Deliverables:

- README
- License
- Governance files
- Documentation structure
- Template structure
- Initial progress tracker

## P1: Core Codex Templates

Goal: Provide the most common Codex task prompts.

Deliverables:

- Initial audit
- Feature implementation
- Bug investigation
- Safe refactoring
- Release check
- Session handoff

## P2: Agent Templates

Goal: Define reusable role-based agents.

Deliverables:

- CEO agent
- PM agent
- Engineer agent
- QA agent
- Release manager agent
- Legal review agent

## P3: Thread Management Templates

Goal: Make long-running app work easier to split and resume.

Deliverables:

- Thread splitting rules
- iOS thread template
- Backend thread template
- Release thread template
- Bugfix thread template

## P4: App Store / TestFlight Templates

Goal: Support distribution workflows for iOS developers.

Deliverables:

- App Store review prompt
- TestFlight preparation prompt
- App Store checklist
- TestFlight checklist
- iOS release checklist
- IAP checklist

## P5: Safety Standards

Goal: Make side-effect, privacy, and sensitive-information safety policies explicit and reusable.

Deliverables:

- P5-1 Mutation Safety Standard
- P5-2 Human Confirmation Standard
- P5-3 Rollback Standard
- P5-4 Sensitive Information Audit
- P5-5 Recurring Privacy & Secret Audit
- P5-6 Security Audit Log
- P5-7 Security reporting policy
- P5-8 Side-effect operation examples

### P5-1 Mutation Safety Standard

Purpose:
Prevent Codex from silently performing create, update, delete, approve, reject, send, publish, release, deploy, upload, submit, or other mutation-sensitive operations.

Completion criteria:

- Mutation-sensitive verbs and operation types are defined.
- Local read-only work is separated from side-effect execution.
- The standard is documented in `docs/safety-standards.md`.
- Templates, agents, threads, and checklists require confirmation before mutation-sensitive operations.

### P5-2 Human Confirmation Standard

Purpose:
Require a complete approval block before risky operations.

Completion criteria:

- Confirmation requires target, payload, impact scope, and rollback.
- Confirmation is specific to the actual operation.
- The standard is documented in `docs/safety-standards.md`.
- Reusable prompts and checklists include or reference the confirmation fields.

### P5-3 Rollback Standard

Purpose:
Make recovery explicit before risky work.

Completion criteria:

- Rollback plan, recovery path, revert method, and known limitations are documented.
- Unknown or partial rollback blocks execution until human risk acceptance.
- The standard is documented in `docs/safety-standards.md`.
- Release, backend, IAP, App Store, TestFlight, and deployment workflows include rollback checks.

### P5-4 Sensitive Information Audit

Purpose:
Audit the repository for personal information, confidential information, credentials, internal information, and commercial service secrets.

Audit examples:

- API keys
- tokens
- secrets
- passwords
- `.env` files
- Firebase plist files
- Apple Developer information
- App Store Connect information
- private email addresses
- personal names
- phone numbers
- addresses
- customer data
- production database URLs
- internal project information
- company confidential information
- unpublished product strategy

Completion criteria:

- The entire repository has received a heavy audit.
- The audit checks suspicious strings, filenames, configuration files, sample data, and docs, not only simple grep results.
- Any issues found are removed or replaced with sample values.
- Audit results are recorded in `progress.md` or `docs/security-audit-log.md`.

### P5-5 Recurring Privacy & Secret Audit

Purpose:
Run recurring checks for personal information, confidential information, and secret leakage before public release, before release operations, and after large changes.

Completion criteria:

- Audit timing is documented.
- The audit is mandatory before public release.
- The workflow explicitly prioritizes deep review over lightweight checks, even if Codex usage increases.

### P5-6 Security Audit Log

Purpose:
Keep a durable history of security and sensitive-information audits.

Required file:

- `docs/security-audit-log.md`

Required log fields:

- audit date
- scope
- commands used
- findings
- actions taken
- residual risk
- next audit

## P6: Real Examples

Goal: Demonstrate the workflow on realistic projects without exposing private data.

Deliverables:

- Example iOS feature workflow
- Example backend bug investigation
- Example release handoff
- Example App Store review preparation
- Example root-cause analysis report

## P7: Public Articles / Promotion

Goal: Explain the workflow publicly and invite contributors.

Deliverables:

- Project announcement
- Blog post on Codex app workflows
- Blog post on human-confirmation rules
- Social post examples
- Demo walkthrough

## P8: Release Preparation

Goal: Prepare stable public releases from v0.1.0 toward v1.0.

Deliverables:

- GitHub release preparation
- Documentation review
- Template review
- Safety review
- Release notes
- Tag and release plan
- Quickstart paths
