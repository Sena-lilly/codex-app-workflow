# Codex vs ChatGPT

Codex and ChatGPT are both useful, but they are best used differently during app development.

## ChatGPT Is Best For

- Brainstorming product ideas
- Explaining concepts
- Comparing approaches
- Drafting copy
- Reviewing architecture at a high level
- Preparing questions before implementation

ChatGPT usually works from the context you provide directly in the conversation.

## Codex Is Best For

- Inspecting a local workspace
- Reading multiple files
- Editing code and documentation
- Running local commands
- Debugging with logs and tests
- Preparing structured diffs
- Building release checklists from real project files

Codex is strongest when it can look at the repository itself and verify its changes.

## Practical Rule

Use ChatGPT to think broadly. Use Codex to work concretely.

For example:

- Ask ChatGPT to compare possible onboarding flows.
- Ask Codex to inspect the SwiftUI project and implement the selected onboarding flow.
- Ask ChatGPT to help refine App Store copy.
- Ask Codex to check release readiness, metadata files, build settings, and checklist status.

## When To Switch To Codex

Switch to Codex when the next step needs:

- File inspection
- Code edits
- Terminal output
- Test results
- Build results
- Repository-specific context

## When To Stay In ChatGPT

Stay in ChatGPT when the work is:

- Exploratory
- Strategy-focused
- Not tied to a specific repository
- Mostly writing or ideation
- Better done without touching local files

## Shared Safety Rule

Both tools should treat side-effect operations carefully.

Codex workflows in this repository require explicit human confirmation before production database writes, external API sends, GitHub pushes, release creation, TestFlight submission, App Store submission, billing changes, or destructive infrastructure actions.
