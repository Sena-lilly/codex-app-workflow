# Public Backlog

This backlog is for public post-launch planning after the repository is available on GitHub.

Use these items as issue candidates. Keep each issue scoped, practical, and grounded in real workflow needs.

## v0.1.1 Candidates

### Side-effect operation examples

Why it matters:

- The safety standards are easier to apply when users can see concrete examples of risky operations and the required human confirmation format.

Expected deliverable:

- Add example snippets for GitHub push, release creation, external API send, production database write, App Store submission, and TestFlight operation requests.

Priority:

- High

Suggested issue label:

- `documentation`
- `safety`

### Security reporting policy

Why it matters:

- Public repositories need a clear path for reporting security or sensitive-information issues without exposing details in public issues.

Expected deliverable:

- Review `SECURITY.md` and add clearer private reporting guidance, supported issue types, expected response expectations, and what not to include in public reports.

Priority:

- High

Suggested issue label:

- `security`
- `documentation`

### README diagram polish

Why it matters:

- The README diagram is the first visual summary of the project. It should stay compact while helping new users understand the workflow quickly.

Expected deliverable:

- Review the ASCII workflow diagram after GitHub rendering, then adjust spacing or wording if needed.

Priority:

- Medium

Suggested issue label:

- `documentation`
- `good first issue`

### Quickstart feedback improvements

Why it matters:

- `docs/quickstart-paths.md` should reflect how users actually enter the project after the first public release.

Expected deliverable:

- Collect early feedback, identify confusing routes, and improve the path descriptions or first-template recommendations.

Priority:

- Medium

Suggested issue label:

- `documentation`
- `feedback`

### Template wording cleanup

Why it matters:

- Small wording differences across templates can make Codex outputs inconsistent.

Expected deliverable:

- Review repeated sections such as Purpose, Inputs, Constraints, Safety rules, Output format, and Done criteria for clearer shared wording.

Priority:

- Medium

Suggested issue label:

- `templates`
- `documentation`

## v0.2.0 Candidates

### Fastlane workflow templates

Why it matters:

- Many iOS teams use Fastlane for screenshots, metadata, build upload, and release preparation.

Expected deliverable:

- Add Codex prompts and checklists for reviewing Fastlane lanes, dry-runs, environment variables, App Store Connect risk, and rollback planning.

Priority:

- Medium

Suggested issue label:

- `ios`
- `release`
- `templates`

### Xcode Cloud workflow templates

Why it matters:

- Xcode Cloud introduces CI, signing, TestFlight, and App Store release concerns that should remain human-confirmed.

Expected deliverable:

- Add templates for auditing Xcode Cloud workflows, build settings, environment variables, signing, test plans, and release gates.

Priority:

- Medium

Suggested issue label:

- `ios`
- `ci`
- `templates`

### GitHub Actions examples

Why it matters:

- Public users may want CI examples for linting, link checks, documentation checks, or app/backend tests.

Expected deliverable:

- Add example GitHub Actions workflow drafts with clear notes that publishing, deployment, and release actions require human confirmation.

Priority:

- Medium

Suggested issue label:

- `ci`
- `examples`

### Backend deployment checklist

Why it matters:

- Backend release work can involve migrations, secrets, production data, and deployment rollback risk.

Expected deliverable:

- Add a backend deployment checklist covering migrations, environment variables, health checks, logs, rollback, and production mutation safety.

Priority:

- High

Suggested issue label:

- `backend`
- `release`
- `safety`

### MCP workflow examples

Why it matters:

- Codex workflows may use MCP-backed tools, and users need examples that separate local inspection from external side effects.

Expected deliverable:

- Add examples showing how to document MCP tool scope, allowed operations, blocked operations, confirmation requirements, and handoff notes.

Priority:

- Low

Suggested issue label:

- `examples`
- `tooling`

## v0.3.0 Candidates

### Multi-agent orchestration examples

Why it matters:

- The agent prompts are useful, but users may need examples showing how CEO, PM, engineer, QA, release manager, and legal review roles work together.

Expected deliverable:

- Add scenario-based examples showing agent sequencing, decision boundaries, escalation points, and final handoff.

Priority:

- Medium

Suggested issue label:

- `agents`
- `examples`

### Real-world case studies

Why it matters:

- Case studies can show where the workflow helps, where it is too heavy, and what should be simplified.

Expected deliverable:

- Add anonymized or fictionalized case studies based on real workflow patterns, without private project details or customer data.

Priority:

- Medium

Suggested issue label:

- `examples`
- `documentation`

### Community contributed workflows

Why it matters:

- Different teams use different stacks, release paths, and safety practices.

Expected deliverable:

- Add contribution guidance for community workflows, including required sections, safety review, and sensitive-information checks.

Priority:

- Medium

Suggested issue label:

- `community`
- `templates`

### Claude Code comparison guide

Why it matters:

- Some users may compare Codex workflows with other coding agents and need a practical migration or comparison guide.

Expected deliverable:

- Add a neutral comparison guide focused on workflow structure, safety rules, handoff patterns, and tool assumptions.

Priority:

- Low

Suggested issue label:

- `documentation`
- `comparison`

### AI app starter integration

Why it matters:

- Starter projects can benefit from including workflow prompts and release safety rules from the beginning.

Expected deliverable:

- Add guidance for integrating these templates into app starter repositories without copying secrets, internal config, or release credentials.

Priority:

- Low

Suggested issue label:

- `integration`
- `templates`
