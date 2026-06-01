# Thread Management

Codex threads work best when each thread has one clear job, one domain, and one handoff.

Use this guide to decide which thread template to start, what context to carry forward, and when to split work before the conversation becomes hard to reason about.

## Quick Decision Table

| Situation | Use This Template | Why |
|---|---|---|
| You are unsure whether to continue or split | [thread-splitting-rules.md](../templates/threads/thread-splitting-rules.md) | Decides whether to continue, split, or finish with handoff |
| The task is SwiftUI, Xcode, simulator, StoreKit, IAP, APIClient, or app-side config | [ios-thread-template.md](../templates/threads/ios-thread-template.md) | Keeps iOS work focused and checks Debug, localhost, App Store, and IAP risks |
| The task is FastAPI, API contract, auth, env, database, migration, mutation safety, or backend tests | [backend-thread-template.md](../templates/threads/backend-thread-template.md) | Keeps backend work focused and protects data/API compatibility |
| The task is observed vs expected behavior, reproduction, logs, root cause, minimal fix, or regression test | [bugfix-thread-template.md](../templates/threads/bugfix-thread-template.md) | Prevents premature fixes and keeps evidence tied to the root cause |
| The task is TestFlight, App Store, backend release, privacy, IAP, review notes, version/build, or go/no-go | [release-thread-template.md](../templates/threads/release-thread-template.md) | Separates readiness review from execution and prepares human confirmation gates |
| The task is privacy, secrets, sensitive information, or security audit | [thread-splitting-rules.md](../templates/threads/thread-splitting-rules.md), then use the relevant audit checklist | Keeps audit work separate from feature or release work |

## Recommended Thread Structure

| Phase | Thread | Main Output |
|---|---|---|
| Project start | Initial audit thread | Repository map, risks, next action |
| Product planning | PM or CEO agent thread | Scope, priorities, acceptance criteria |
| iOS implementation | iOS thread | Scoped app-side diff and verification |
| Backend implementation | Backend thread | Scoped API/backend diff and verification |
| Bug investigation | Bugfix thread | Root cause, minimal fix, regression checks |
| Release readiness | Release thread | GO / GO WITH RISKS / NO-GO |
| Security/privacy review | Audit-focused thread | Findings, actions, residual risk |
| Thread transition | Session handoff | Current state and next prompt |

## When To Split

Start a new thread when:

- The domain changes between iOS, backend, bugfix, release, QA, legal, privacy, audit, or docs
- A feature implementation turns into a bug investigation
- A bug investigation becomes implementation
- Implementation becomes release readiness
- Release work involves TestFlight, App Store, backend deployment, privacy, IAP, or migration risk
- Security or privacy audit work begins
- Context overflow is likely
- The current work cannot be summarized in a short handoff

## When Not To Split

Stay in the current thread when:

- The next step is still the same goal and domain
- The context is short and easy to summarize
- The change is a small continuation of the current task
- Splitting would force the next thread to rediscover the same files and decisions
- You only need to run one more local verification check before handoff

## Context Overflow Rule

If the current thread cannot be summarized in under 10 bullets, split it.

Before splitting, produce a handoff with:

- Goal
- Current state
- Completed work
- Not completed work
- Important decisions
- Files changed
- Commands run
- Verification results
- Known issues and risks
- Next prompt

Use [session-handoff.md](../templates/codex/session-handoff.md).

## Feature / Bugfix / Release / Audit Separation

Keep these concerns separate:

- Feature threads decide and implement scoped behavior.
- Bugfix threads prove observed vs expected behavior and root cause before fixing.
- Release threads assess readiness and prepare human confirmation gates.
- Audit threads search for privacy, secret, safety, or compliance risk.

Do not let a release thread quietly become an implementation thread. Do not let a bugfix thread become a broad refactor. Do not let a feature thread execute release actions.

## What To Carry Forward

Carry forward:

- The goal
- Acceptance criteria or release criteria
- Files changed or inspected
- Commands run and results
- Important decisions and tradeoffs
- Known risks and blockers
- Human-confirmation items
- The next prompt

Do not carry forward:

- Full chat history
- Secrets or private data
- Irrelevant brainstorming
- Unverified assumptions
- Commands that should execute automatically

## Thread Naming

Use names that include the domain and objective:

- `ios-onboarding-flow`
- `backend-auth-contract`
- `bugfix-login-timeout`
- `release-testflight-1.2.0`
- `audit-sensitive-information`

## Safety Rule

Threads that may touch external systems must include human-confirmation requirements before side-effect operations.

Do not execute these without explicit human confirmation:

- GitHub push, tag, or release creation
- Backend deployment
- Production database write or migration
- External API send, email, notification, or webhook
- App Store submission
- TestFlight submission
- IAP, billing, signing, or provisioning changes

When confirmation is needed, present:

- target command / endpoint / screen
- payload or operation details
- impact scope
- rollback plan
