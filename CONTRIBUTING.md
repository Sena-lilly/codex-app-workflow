# Contributing

Thank you for helping improve `codex-app-workflow`.

This project is a workflow kit, so contributions should make Codex-based app development safer, clearer, or more repeatable.

## Good Contributions

Useful contributions include:

- New Codex prompt templates
- Improvements to agent role definitions
- Thread-management patterns from real projects
- Release and review checklists
- Safer wording for human-confirmation steps
- Real examples with private information removed

## Template Style

Templates should be:

- Practical enough to copy into Codex directly
- Specific about expected inputs and outputs
- Clear about verification steps
- Conservative around side effects
- Short enough to use during real work

Avoid templates that are purely motivational or too abstract to execute.

## Safety Requirements

Any contribution that mentions side-effect operations must include a human-confirmation step.

Side-effect operations include:

- Production database writes
- External API sends
- GitHub pushes
- Release creation
- App Store or TestFlight submission
- Billing, subscription, or IAP configuration changes
- Destructive infrastructure changes

Before any such operation, the workflow must ask the human to confirm:

- Target command
- Target resources
- Expected impact
- Rollback method

## Pull Request Checklist

Before opening a pull request:

- [ ] The change is scoped to one workflow concern.
- [ ] New templates include inputs, steps, outputs, and verification guidance.
- [ ] Safety-sensitive workflows include human-confirmation rules.
- [ ] No private project names, credentials, or customer data are included.
- [ ] Markdown links are valid.

## Local Review

Recommended local checks:

```sh
rg "TODO|FIXME|SECRET|TOKEN|PASSWORD|API_KEY"
rg --files
```

This repository is documentation-first, so manual review matters more than automated checks at the bootstrap stage.
