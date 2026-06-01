# Safety Standards

These standards define how Codex workflows in this repository handle mutations, human confirmation, and rollback planning.

Use this document as the source of truth when reviewing README content, docs, prompts, checklists, agents, and thread templates.

## P5-1: Mutation Safety Standard

## Purpose

Prevent Codex from silently performing operations that create, update, delete, approve, reject, send, publish, release, deploy, or otherwise mutate real systems, user data, business state, billing state, repository history, or distribution channels.

## Mutation Operations

Treat these as mutation or side-effect operations:

- create
- update
- delete
- approve
- reject
- send
- publish
- release
- deploy
- upload
- submit
- merge
- tag
- notify
- migrate
- rotate
- grant access
- revoke access
- modify production data
- change billing, IAP, signing, provisioning, or availability

## Standard

- Codex may inspect, draft, edit local documentation, run safe local checks, and prepare commands.
- Codex must not execute real-world mutation operations without explicit human confirmation.
- Mutation-sensitive prompts must separate readiness review from execution.
- Release, deployment, billing, App Store, TestFlight, GitHub, external API, production database, and access-control operations are high risk by default.

## P5-2: Human Confirmation Standard

## Purpose

Ensure that the human can approve or reject a risky operation with enough context before anything is executed.

## Required Confirmation Fields

Before any mutation or side-effect operation, Codex must present:

- target: command, endpoint, screen, service, file, or resource
- payload: request body, operation details, settings, metadata, or manual changes
- impact scope: users, data, environments, releases, billing, repositories, or external systems affected
- rollback: rollback plan, recovery path, revert method, and known limitations

## Standard Confirmation Block

```md
Human confirmation required.

Target:
[command / endpoint / screen / resource]

Payload / operation details:
[exact payload, settings, metadata, or manual change]

Impact scope:
[who or what is affected]

Rollback:
- rollback plan:
- recovery path:
- revert method:
- known limitations:

Please confirm before I proceed.
```

General approval such as "ship it" or "do the release" is not enough. Confirmation must match the actual operation, target, payload, impact scope, and rollback limits.

## P5-3: Rollback Standard

## Purpose

Make recovery explicit before performing risky work.

## Required Rollback Fields

Every risky operation must document:

- rollback plan: what should happen if the operation fails or causes harm
- recovery path: how the project returns to a known-safe state
- revert method: exact command, manual step, version rollback, config reversal, feature flag, or support action
- known limitations: what cannot be fully undone, what may require support, review delay, data repair, or user communication

## Standard

- If rollback is unknown, mark the operation as blocked until a human owner accepts the risk.
- If rollback is partial, state the limitation before asking for approval.
- If rollback affects production data, billing, IAP, App Store, TestFlight, or deployed services, require explicit human confirmation.
- If the safest option is a dry-run, staging check, feature flag, or backup first, recommend that before execution.

## Repository Application

These standards apply to:

- README safety guidance
- docs
- Codex templates
- checklists
- agent prompts
- thread templates
- release workflows
- privacy and security audit workflows

Standalone templates may repeat the safety language so they remain safe when copied out of context. This document remains the canonical standard.
