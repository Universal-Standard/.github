# Contributing to Universal Standard

Thanks for your interest in contributing. This file is an organization-wide
default — repositories under `Universal-Standard` inherit it automatically
unless they define their own `CONTRIBUTING.md`.

## Before you start

- Read the [Code of Conduct](./CODE_OF_CONDUCT.md).
- Search existing [issues](https://github.com/search?q=org%3AUniversal-Standard&type=issues)
  and open pull requests before filing a new one, to avoid duplicates.
- For anything nontrivial (new feature, architecture change, new standard),
  open an issue first to discuss the approach before writing code.

## Workflow

1. **Fork** the repository (or create a feature branch if you have write
   access).
2. **Branch naming**: `type/short-description`, e.g. `feat/oauth-support`,
   `fix/null-pointer-manifest-loader`, `docs/update-readme`.
3. **Commit messages**: follow [Conventional Commits](https://www.conventionalcommits.org/)
   (`feat:`, `fix:`, `docs:`, `chore:`, `refactor:`, `test:`) so changelogs
   and release automation stay accurate.
4. **Keep pull requests focused.** One logical change per PR. Large,
   unrelated changes take longer to review and are more likely to be
   rejected.
5. **Tests.** Add or update tests for any behavior change. PRs that reduce
   test coverage without justification will be asked to add it back.
6. **Lint / format.** Run the repository's configured linter and formatter
   before pushing (see that repo's `package.json` scripts or `Makefile`).
   Most repositories run these automatically in CI on every PR.
7. **Fill out the PR template.** It exists to make review faster, not to
   slow you down — a two-line summary and a checked checklist is enough for
   small changes.

## Coding standards

Cross-project engineering standards (naming conventions, API design,
security baselines, documentation requirements) live in the
[`standards`](https://github.com/UniversalStandards/UniversalStandards/tree/main/standards)
directory. When a repository's local conventions conflict with the org-wide
standards, the org-wide standards win unless the repository explicitly
documents and justifies the deviation.

## Local development environment

Repositories that support GitHub Codespaces will pick up their own
`.devcontainer/devcontainer.json` if present. If you use GitHub Codespaces
across multiple `Universal-Standard` repositories and want your personal
shell/editor setup to follow you automatically, configure your own
**personal** dotfiles repository under Settings → Codespaces → Dotfiles.
That is separate from this repository and is not something a maintainer can
set on your behalf.

## Reporting a bug or requesting a feature

Use the issue templates — they route to the right triage queue and ask for
the information maintainers need to act quickly. Issues opened without the
template's required fields may be closed and asked to be reopened with more
detail.

## Reporting a security vulnerability

Do **not** open a public issue for a security vulnerability. See
[SECURITY.md](./SECURITY.md).

## Review and merge

- A maintainer will review your PR. Expect at least one round of feedback
  on nontrivial changes.
- CI must pass before merge.
- Maintainers merge using squash-merge by default to keep history readable,
  unless a repository's own contributing notes say otherwise.

## Questions

If something here doesn't match a specific repository's actual practice,
that repository's own `CONTRIBUTING.md` (if any) takes precedence — open an
issue on this `.github` repository if you think the org-wide default itself
needs updating.
