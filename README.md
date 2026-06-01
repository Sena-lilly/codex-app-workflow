# codex-app-workflow

A practical workflow kit for building, debugging, reviewing, and shipping apps with Codex.

This repository provides reusable prompts, agent role templates, thread-management rules, and release checklists for developers who want to use Codex as part of a serious app development workflow.

## Start Here

Step 1: Read this README.

Step 2: Read the [Examples](#examples).

Step 3: Pick a template from [Included Templates](#included-templates).

Step 4: Start your Codex thread with the selected prompt.

## What is this?

`codex-app-workflow` is an OSS template for running app development work with Codex in a repeatable way.

It focuses on the workflows around implementation, investigation, review, release preparation, and human confirmation. The goal is not to replace engineering judgment. The goal is to make the judgment easier to apply consistently.

## Who is this for?

This project is designed for:

- Independent iOS developers
- SwiftUI developers
- Developers building apps with FastAPI or backend services
- Builders who want to use Codex from early development through TestFlight, App Store review, and release operations
- Small teams that need lightweight process without heavy project-management tooling

## Why this exists

Codex is powerful when it can inspect a workspace, run commands, edit files, and verify behavior. That same power needs structure.

This repository exists to make common Codex workflows safer and more repeatable:

- Start new projects with a clear audit process
- Split large work into focused threads
- Use role-specific agents for product, engineering, QA, release, and legal review
- Keep release work gated by human confirmation
- Avoid accidental side effects such as production database writes, external API calls, GitHub pushes, or App Store submissions

## Quick Start

1. Clone or copy this repository.
2. Read [docs/philosophy.md](docs/philosophy.md).
3. Start with [templates/codex/initial-audit.md](templates/codex/initial-audit.md) in a new Codex thread.
4. Use [templates/threads/thread-splitting-rules.md](templates/threads/thread-splitting-rules.md) when work becomes too broad.
5. Track project setup and release readiness in [progress.md](progress.md).

For release work, begin with:

- [templates/codex/release-check.md](templates/codex/release-check.md)
- [templates/checklists/testflight-checklist.md](templates/checklists/testflight-checklist.md)
- [templates/checklists/app-store-checklist.md](templates/checklists/app-store-checklist.md)

## Included Templates

Codex task templates:

- [Initial audit](templates/codex/initial-audit.md)
- [Feature implementation](templates/codex/implement-feature.md)
- [Bug investigation](templates/codex/bug-investigation.md)
- [Safe refactoring](templates/codex/refactor-safely.md)
- [Release check](templates/codex/release-check.md)
- [App Store review](templates/codex/app-store-review.md)
- [TestFlight preparation](templates/codex/testflight-prep.md)
- [Session handoff](templates/codex/session-handoff.md)

Agent templates:

- [CEO agent](templates/agents/ceo-agent.md)
- [PM agent](templates/agents/pm-agent.md)
- [Engineer agent](templates/agents/engineer-agent.md)
- [QA agent](templates/agents/qa-agent.md)
- [Release manager agent](templates/agents/release-manager-agent.md)
- [Legal review agent](templates/agents/legal-review-agent.md)

Thread templates:

- [Thread splitting rules](templates/threads/thread-splitting-rules.md)
- [iOS thread template](templates/threads/ios-thread-template.md)
- [Backend thread template](templates/threads/backend-thread-template.md)
- [Release thread template](templates/threads/release-thread-template.md)
- [Bugfix thread template](templates/threads/bugfix-thread-template.md)

Checklists:

- [App Store checklist](templates/checklists/app-store-checklist.md)
- [TestFlight checklist](templates/checklists/testflight-checklist.md)
- [iOS release checklist](templates/checklists/ios-release-checklist.md)
- [Backend release checklist](templates/checklists/backend-release-checklist.md)
- [Privacy checklist](templates/checklists/privacy-checklist.md)
- [IAP checklist](templates/checklists/iap-checklist.md)
- [Safety checklist](templates/checklists/safety-checklist.md)

## Examples

Practical end-to-end examples:

- [iOS feature workflow](examples/ios-feature-example.md)
- [Backend bug investigation](examples/backend-bug-investigation-example.md)
- [App Store release readiness](examples/app-store-release-example.md)
- [Release session handoff](examples/session-handoff-example.md)

## Recommended Workflow

1. Run an [initial audit](templates/codex/initial-audit.md) before implementation.
2. Create one focused thread per major concern: iOS, backend, release, bugfix, or review.
3. Use the relevant [Codex task template](templates/codex/implement-feature.md) for the current phase.
4. Keep agent templates role-specific. Do not let one agent own every decision.
5. Require human confirmation for side-effect operations.
6. Prefer dry-runs, local checks, and root-cause analysis before making broad changes.
7. End each session with a [handoff](templates/codex/session-handoff.md) that records decisions, changed files, verification results, and next steps.

Important safety rule:

Do not perform production database writes, external API sends, GitHub pushes, release creation, App Store submissions, TestFlight submissions, billing changes, or destructive infrastructure operations without explicit human confirmation.

See [docs/safety-standards.md](docs/safety-standards.md) for the canonical mutation, confirmation, and rollback standards.

When a side-effect operation is needed, present:

- Target
- Payload or operation details
- Impact scope
- Rollback plan, recovery path, revert method, and known limitations

## Roadmap

The current roadmap is organized as P0 through P8:

- P0: Repository Bootstrap
- P1: Core Codex Templates
- P2: Agent Templates
- P3: Thread Management Templates
- P4: App Store / TestFlight Templates
- P5: Safety Standards
- P6: Real Examples
- P7: Public Articles / Promotion
- P8: Release Preparation

See [docs/roadmap.md](docs/roadmap.md) and [progress.md](progress.md).

For the first public-ready package, see [CHANGELOG.md](CHANGELOG.md) and [docs/release-notes-v0.1.0.md](docs/release-notes-v0.1.0.md).

## Contributing

Contributions are welcome. Please start with [CONTRIBUTING.md](CONTRIBUTING.md), keep templates practical, and include safety guidance whenever a workflow may cause real-world side effects.

## License

MIT License. See [LICENSE](LICENSE).
