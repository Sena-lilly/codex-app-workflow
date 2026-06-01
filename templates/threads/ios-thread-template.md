# iOS Thread Template

Copy the prompt below into a new Codex thread for focused iOS, SwiftUI, Xcode, simulator, StoreKit, or App Store configuration work.

```md
# iOS Thread Prompt

## Thread purpose

Work on one focused iOS task while preserving project safety, release settings, and handoff quality.

## When to create this thread

Create an iOS thread when the task involves:

- SwiftUI UI or app flow
- Xcode project settings
- Build errors or archive errors
- Simulator behavior
- APIClient or networking from the app
- StoreKit, IAP, subscriptions, restore purchases, or entitlements
- App Store related settings, permissions, metadata, or review readiness
- Localhost, Debug, staging, or production API configuration

## What context to include

Include:

- Goal
- App target or scheme
- Affected screens, views, models, services, or files
- Acceptance criteria
- Device/simulator and OS version if relevant
- Build or test command if known
- API base URL expectations
- StoreKit/IAP context if relevant
- App Store or signing/provisioning context if relevant

## What not to include

Do not include:

- Backend implementation details unless they affect the iOS contract
- Full previous transcript
- Real credentials, API keys, provisioning secrets, or private Apple account details
- App Store Connect changes to execute automatically
- TestFlight or App Store submission instructions to run without approval

## Allowed scope

Allowed work:

- Inspect Swift, SwiftUI, asset, project, test, and configuration files
- Diagnose local build or simulator issues
- Implement scoped iOS changes
- Update local tests or docs when needed
- Run safe local build/test commands
- Prepare but not execute release or App Store/TestFlight operations

## Out-of-scope items

Do not:

- Change backend behavior unless explicitly requested
- Change public API contracts without backend coordination
- Change signing, provisioning, IAP products, App Store Connect, or TestFlight settings without approval
- Upload builds
- Submit to App Store or TestFlight
- Push to GitHub

## Safety rules

Do not perform these without explicit human confirmation:

- Production database writes or migrations
- External API sends, emails, notifications, or webhooks
- GitHub push, git tag, or GitHub release creation
- Release creation, deployment, or package publishing
- App Store submission or TestFlight submission
- Billing, subscription, IAP, signing, or provisioning changes
- Destructive file, infrastructure, or data operations

If a side-effect operation is needed, stop and present:

- target command / endpoint / screen
- payload or operation details
- impact scope
- rollback plan

## Required first actions

1. Identify the iOS target, scheme, and affected files.
2. Inspect relevant SwiftUI, APIClient, asset, test, and Xcode project files.
3. Check for Debug-only behavior, localhost URLs, staging/production URLs, and hardcoded config.
4. Identify whether StoreKit/IAP, signing/provisioning, or App Store settings are involved.
5. State the minimal plan before editing.
6. Identify safe local checks to run.

## Output format

Return exactly these sections:

## Goal

## iOS Context

Include target, scheme, simulator/device, and relevant files.

## Investigation

## Minimal Plan

## Changes Made

## Build / Test / Simulator Checks

For each check include:
- command or manual check
- result
- notes

## APIClient / Localhost / Debug Notes

## StoreKit / IAP / App Store Notes

## Files Changed

## Risks / Follow-ups

## Human Confirmation Needed

For each item include:
- target command / endpoint / screen
- payload or operation details
- impact scope
- rollback plan

## Handoff format

End with:

## Goal

## Current State

## Completed

## Not Completed

## Important Decisions

## Files Changed

## Commands Run

## Checks / Verification

## Known Issues / Risks

## Next Prompt

## Done criteria

This iOS thread is done when:

- The iOS task is scoped to app-side work.
- SwiftUI/Xcode/APIClient/StoreKit/App Store concerns are checked where relevant.
- Localhost and Debug configuration are reviewed when networking is involved.
- Relevant local checks are run or clearly blocked.
- Side-effect operations are prepared for human confirmation but not executed.
- A handoff is provided.
```
