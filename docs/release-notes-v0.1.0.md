# Release Notes: v0.1.0

## What is included

v0.1.0 is the first public-ready documentation release of `codex-app-workflow`.

It includes:

- Core Codex prompts for audits, implementation, bug investigation, refactoring, release checks, App Store review, TestFlight preparation, and session handoff.
- Role prompts for CEO, PM, engineer, QA, release manager, and legal review agents.
- Thread-management prompts for iOS, backend, release, bugfix, and context-splitting workflows.
- App Store, TestFlight, iOS release, backend release, privacy, IAP, and safety checklists.
- Safety standards for side-effect operations, human confirmation, rollback planning, and sensitive information audits.
- Example workflows that show realistic prompts, expected Codex behavior, expected outputs, and handoff examples.

## Who should use this

This release is intended for:

- Independent iOS developers using Codex during app development.
- SwiftUI developers who want repeatable implementation and review prompts.
- Backend developers using FastAPI or similar service architectures.
- Developers preparing apps for TestFlight, App Store review, or backend release readiness.
- Small teams that want lightweight agent roles, thread separation, and safety rules without adopting heavy process tooling.

## Known limitations

- This repository is a workflow kit, not an executable app framework.
- The templates are intentionally generic and should be adapted to each codebase before use.
- The App Store, TestFlight, privacy, legal, and IAP materials are operational checklists, not legal advice.
- The release does not automate GitHub publishing, App Store Connect actions, TestFlight operations, external API calls, or production deployments.
- Example projects use fictional names only and are not complete application repositories.
- Public article and promotion materials are still planned for a later phase.

## Roadmap

Near-term priorities:

- Complete remaining P5 safety documentation items, including pre-release and recurring audit procedures.
- Prepare P7 public articles and promotional material.
- Finalize P8 release planning, including tag strategy and maintainer checklist.
- Continue improving examples based on real-world Codex app-development workflows.

Longer-term priorities:

- Add more domain-specific examples for SwiftUI, StoreKit, FastAPI, authentication, and database migrations.
- Expand release-management guidance for multi-platform apps.
- Collect community feedback and stabilize the templates for v1.0.

