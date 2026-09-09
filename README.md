# .github

This is the **organization-wide default community health files** repository
for [`Universal-Standard`](https://github.com/Universal-Standard). GitHub
automatically applies the files in here to any repository owned by this
organization that does not define its own copy.

## What's in here and why

| File | Applies to a repo when... | Fallback location precedence |
|---|---|---|
| [`CODE_OF_CONDUCT.md`](./CODE_OF_CONDUCT.md) | it has no `CODE_OF_CONDUCT.md` of its own | `.github/` → root → `docs/` |
| [`CONTRIBUTING.md`](./CONTRIBUTING.md) | it has no `CONTRIBUTING.md` of its own | `.github/` → root → `docs/` |
| [`SECURITY.md`](./SECURITY.md) | it has no `SECURITY.md` of its own | `.github/` → root → `docs/` |
| [`SUPPORT.md`](./SUPPORT.md) | it has no `SUPPORT.md` of its own | `.github/` → root → `docs/` |
| [`GOVERNANCE.md`](./GOVERNANCE.md) | it has no `GOVERNANCE.md` of its own | `.github/` → root → `docs/` |
| [`.github/PULL_REQUEST_TEMPLATE.md`](./.github/PULL_REQUEST_TEMPLATE.md) | it has no PR template of its own | same |
| [`.github/ISSUE_TEMPLATE/`](./.github/ISSUE_TEMPLATE/) | it has **no files at all** in its own `.github/ISSUE_TEMPLATE/` folder (partial overrides are not merged — a repo with any issue template of its own ignores all of these) | n/a |
| [`profile/README.md`](./profile/README.md) | — | shown on the organization's public GitHub profile page, not a per-repo fallback |

## What is deliberately *not* here

- **`CODEOWNERS`** — GitHub does not support an organization-wide default
  `CODEOWNERS` file. Each repository that wants code-owner review
  enforcement needs its own `CODEOWNERS` file (root, `.github/`, or
  `docs/`).
- **`LICENSE`** — license files cannot be inherited as an org default and
  must be added per repository.

## Requirements for this mechanism to work

- This repository must be named exactly `.github`.
- It must be **public**. A private `.github` repository (see
  `Universal-Standard/.github-private`, which serves a different purpose —
  internal agent/automation configuration, not community health defaults)
  does not provide organization-wide fallback.

## Changing something here

Open a pull request. Because a change here affects every repository in the
organization that doesn't override it, call that out explicitly in the PR
description. See [GOVERNANCE.md](./GOVERNANCE.md) for how cross-cutting
changes get decided.
