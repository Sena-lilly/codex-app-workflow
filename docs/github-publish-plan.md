# GitHub Publish Plan

This plan prepares the first public GitHub publication for `codex-app-workflow`.

Do not run GitHub push, repository creation, tag creation, release creation, or external publishing commands until a human explicitly confirms them.

## Repository Settings

Repository name:

- `codex-app-workflow`

Visibility:

- Public

GitHub repository creation settings:

- Initialize README: OFF
- Add .gitignore: OFF
- License: OFF

Reason:

- This local repository already contains `README.md`, `.gitignore`, and `LICENSE`.
- Creating these files again on GitHub may cause an avoidable merge conflict.

## Human Commands After GitHub Repository Creation

After a human creates the empty GitHub repository, run these commands manually from the repository root:

```sh
git remote add origin <GitHub repository URL>
git branch -M main
git push -u origin main
```

Do not run these commands until:

- The GitHub repository URL is confirmed.
- The repository is confirmed to be empty.
- The repository visibility is confirmed as Public.
- The local commit is reviewed.

## Pre-Tag and Pre-Release Checklist for v0.1.0

Before creating a `v0.1.0` tag or GitHub release, confirm:

- README displays correctly on GitHub.
- `docs/` files display correctly on GitHub.
- `examples/` files display correctly on GitHub.
- `templates/` files display correctly on GitHub.
- No secrets, private data, production credentials, signing files, Firebase plist files, or `.env` files are present.
- Relative links resolve.
- `CHANGELOG.md` exists and includes `v0.1.0`.
- `docs/release-notes-v0.1.0.md` exists.
- `docs/security-audit-log.md` exists.
- Issue templates are visible in GitHub issue creation.
- Pull request template is visible when opening a PR.

Recommended manual tag and release flow after the checklist passes:

1. Review the first public commit.
2. Create the `v0.1.0` tag locally only after human confirmation.
3. Push the tag only after human confirmation.
4. Create the GitHub release only after human confirmation.

## Rollback

### Remote setting was wrong

Inspect the current remote:

```sh
git remote -v
```

If only the URL is wrong:

```sh
git remote set-url origin <correct GitHub repository URL>
```

If the remote should be recreated:

```sh
git remote remove origin
git remote add origin <correct GitHub repository URL>
```

Confirm again:

```sh
git remote -v
```

### Commit should be changed before push

If the commit has not been pushed yet, keep the fix local:

```sh
git status
git add .
git commit --amend
```

If the commit should be split or rebuilt before push, make a local-only recovery plan first and confirm the exact command before running history-changing operations.

### Secret found after public publication

Treat this as an incident, not a normal documentation fix.

Immediate actions:

- Rotate or revoke the exposed secret at the provider first.
- Remove the secret from the repository content.
- Commit a remediation change.
- Review whether Git history must be rewritten.
- If history rewrite is required, prepare the exact command, impact scope, and rollback plan before running it.
- Communicate the incident to affected maintainers or users if necessary.

Do not rely on deleting the file alone. If a secret reached public Git history, assume it was exposed.

