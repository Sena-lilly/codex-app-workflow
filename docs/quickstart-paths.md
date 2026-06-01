# Quickstart Paths

Use this guide when you know what you want to do, but you are not sure which template to open first.

Default rule:

- If you are new to the repository, start with [initial-audit.md](../templates/codex/initial-audit.md).
- If the task is already clear, use the route below that matches your current goal.
- If a task may cause side effects, require human confirmation before running it.

Side effects include create, update, delete, approve, reject, send, publish, release, deploy, production database writes, external API sends, GitHub pushes, App Store submissions, and TestFlight operations.

## I want to audit an existing app

Use this route when you are opening an unfamiliar app, inheriting a codebase, or preparing Codex before implementation.

Read in this order:

1. [initial-audit.md](../templates/codex/initial-audit.md)
2. [thread-splitting-rules.md](../templates/threads/thread-splitting-rules.md)
3. [safety-checklist.md](../templates/checklists/safety-checklist.md)
4. [session-handoff.md](../templates/codex/session-handoff.md)

First prompt to copy:

- [initial-audit.md](../templates/codex/initial-audit.md)

Expected result:

- Repo structure, build/test commands, environment requirements, secret risks, API/DB risks, P0/P1/P2 findings, and next actions.

## I want to implement a new feature

Use this route when the goal, acceptance criteria, and target area are known.

Read in this order:

1. [implement-feature.md](../templates/codex/implement-feature.md)
2. [engineer-agent.md](../templates/agents/engineer-agent.md)
3. [qa-agent.md](../templates/agents/qa-agent.md)
4. [session-handoff.md](../templates/codex/session-handoff.md)

First prompt to copy:

- [implement-feature.md](../templates/codex/implement-feature.md)

Expected result:

- Investigation before edits, a small implementation plan, minimal diff, test plan, rollback notes, and a clear completion summary.

## I want to investigate a bug

Use this route when behavior is wrong but the root cause is not known.

Read in this order:

1. [bug-investigation.md](../templates/codex/bug-investigation.md)
2. [bugfix-thread-template.md](../templates/threads/bugfix-thread-template.md)
3. [qa-agent.md](../templates/agents/qa-agent.md)
4. [session-handoff.md](../templates/codex/session-handoff.md)

First prompt to copy:

- [bug-investigation.md](../templates/codex/bug-investigation.md)

Expected result:

- Reproduction notes, observed/expected behavior, logs, suspected causes, root cause, fix options, and regression-test guidance.

## I want to prepare for TestFlight

Use this route before uploading a build, adding testers, or asking for beta review.

Read in this order:

1. [testflight-prep.md](../templates/codex/testflight-prep.md)
2. [testflight-checklist.md](../templates/checklists/testflight-checklist.md)
3. [ios-release-checklist.md](../templates/checklists/ios-release-checklist.md)
4. [release-manager-agent.md](../templates/agents/release-manager-agent.md)

First prompt to copy:

- [testflight-prep.md](../templates/codex/testflight-prep.md)

Expected result:

- Archive readiness, build processing checks, tester-group plan, beta instructions, known issues, feedback flow, and human-confirmed action list.

Do not let Codex upload builds, change App Store Connect settings, invite testers, or submit beta review without explicit human confirmation.

## I want to prepare for App Store review

Use this route before submitting metadata, privacy answers, IAP details, or a build for App Store review.

Read in this order:

1. [app-store-review.md](../templates/codex/app-store-review.md)
2. [app-store-checklist.md](../templates/checklists/app-store-checklist.md)
3. [privacy-checklist.md](../templates/checklists/privacy-checklist.md)
4. [iap-checklist.md](../templates/checklists/iap-checklist.md)
5. [legal-review-agent.md](../templates/agents/legal-review-agent.md)

First prompt to copy:

- [app-store-review.md](../templates/codex/app-store-review.md)

Expected result:

- Metadata readiness, privacy risks, IAP/subscription risks, review notes, demo account requirements, common blockers, and App Store Connect actions prepared but not executed.

Do not let Codex submit to App Store review, change pricing, edit IAP products, change privacy answers, or modify App Store Connect settings without explicit human confirmation.

## I want to manage a long Codex session safely

Use this route when work is growing across features, bugs, releases, audits, or multiple platforms.

Read in this order:

1. [thread-splitting-rules.md](../templates/threads/thread-splitting-rules.md)
2. [thread-management.md](thread-management.md)
3. [session-handoff.md](../templates/codex/session-handoff.md)
4. [safety-standards.md](safety-standards.md)

First prompt to copy:

- [thread-splitting-rules.md](../templates/threads/thread-splitting-rules.md)

Expected result:

- Clear thread boundaries, reduced context drift, separate release/audit work, safer handoffs, and explicit next prompts for continuation.

