# Public Announcement Draft

Use this after the GitHub repository is public. Replace `<GitHub repository URL>` before posting.

## Short announcement

I published `codex-app-workflow`, a practical workflow kit for app development with Codex.

It collects reusable prompts, role prompts, thread templates, release checklists, examples, and safety standards for developers who want to use Codex across app audits, feature work, bug investigation, TestFlight preparation, App Store review, and longer development sessions.

GitHub: `<GitHub repository URL>`

## Longer announcement

I published `codex-app-workflow`.

It is a documentation-first workflow kit for building, debugging, reviewing, and preparing apps with Codex. The goal is simple: make Codex-based app development easier to repeat without losing context, skipping safety checks, or mixing release operations into ordinary implementation work.

## Why I made it

Codex is useful when it can inspect a project, run local checks, edit files, and summarize what changed. But app development also includes decisions that should stay explicit:

- Which thread should own the work?
- What should Codex inspect before editing?
- Which files are allowed or out of scope?
- What checks should be run before saying done?
- Which operations require human confirmation?
- How should a long session be handed off safely?

This repository turns those questions into reusable prompts and checklists.

## Who it is for

This is mainly for:

- Independent iOS developers
- SwiftUI developers
- Developers building apps with FastAPI or backend services
- Developers preparing for TestFlight or App Store review
- Small teams using Codex without a heavy process layer

## What is included

- Core Codex templates for audits, implementation, bugs, refactoring, release checks, and handoff
- Agent role prompts for CEO, PM, engineer, QA, release manager, and legal review
- Thread templates for iOS, backend, release, bugfix, and long-session management
- App Store, TestFlight, privacy, IAP, backend release, and safety checklists
- Example workflows showing what to paste, what Codex should investigate, and what output to expect
- Safety standards for side-effect operations, human confirmation, rollback, and sensitive information audits

## Examples

The repository includes example workflows for:

- iOS feature implementation
- Backend bug investigation
- App Store release readiness
- Session handoff

These are intentionally fictional and use sample app names only.

## Safety standards

The project treats side-effect operations as high risk by default.

Examples include:

- GitHub push
- release creation
- external API sends
- production database writes
- App Store submission
- TestFlight operations
- billing or pricing changes

Before any such action, the workflow asks Codex to present:

- target
- payload or operation details
- impact scope
- rollback plan

## Known limitations

- This is a workflow kit, not an executable framework.
- Templates should be reviewed and adapted to each codebase.
- App Store, privacy, legal, and IAP materials are operational checklists, not legal advice.
- The examples are not complete apps.
- The project is early and will need feedback from real use.

GitHub: `<GitHub repository URL>`

