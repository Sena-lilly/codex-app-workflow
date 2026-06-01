# Agent Design

Agent templates define the role Codex should play in a focused thread.

The goal is not to create fictional authority. The goal is to make responsibilities, decision boundaries, and outputs explicit.

## Design Goals

Good agents are:

- Focused on one role
- Clear about what they can decide
- Clear about what they must escalate
- Practical about inputs and outputs
- Conservative around safety-sensitive operations

## Recommended Agent Structure

Each agent template should include:

- Mission
- Responsibilities
- Non-goals
- Required inputs
- Working process
- Output format
- Human-confirmation rules
- Handoff format

## Authority Levels

Use simple authority levels:

- Recommend: The agent can suggest a path.
- Prepare: The agent can draft files, commands, plans, or checklists.
- Execute locally: The agent can make local workspace changes and run local checks.
- Requires confirmation: The agent must stop and ask before side effects.

## Side Effects That Require Confirmation

Agents must not perform these actions without explicit human approval:

- Production database writes
- External API sends
- GitHub pushes
- Release creation
- App Store submission
- TestFlight submission
- Billing or IAP changes
- Destructive infrastructure operations

Before asking for approval, the agent should present:

- target
- payload or operation details
- impact scope
- rollback plan, recovery path, revert method, and known limitations

## Agent Collaboration

For complex app work, use multiple focused threads instead of one large agent:

- CEO agent clarifies strategy and scope.
- PM agent defines requirements and acceptance criteria.
- Engineer agent implements and verifies.
- QA agent tests behavior and edge cases.
- Release manager agent prepares release operations.
- Legal review agent checks privacy, policy, and compliance risk.

## Anti-Patterns

Avoid agents that:

- Own every decision
- Skip verification
- Hide uncertainty
- Execute production changes automatically
- Mix product, engineering, QA, release, and legal responsibilities into one vague role
