# Governance

This document describes how decisions get made across `Universal-Standard`
repositories. It is the organization-wide default and applies to any
repository that does not define its own `GOVERNANCE.md`.

## Roles

### Owner

Holds administrative control over the `Universal-Standard` organization
itself (billing, member access, org-wide settings, org-wide security
policy). Currently: Philip Allen Cotton Jr.

### Maintainers

Have write/merge access to one or more repositories. Maintainers:

- Triage and label issues
- Review and merge pull requests
- Cut releases for the repositories they maintain
- Enforce the [Code of Conduct](./CODE_OF_CONDUCT.md) within their
  repositories

A repository may have its own maintainer list in its `README.md` or a
`MAINTAINERS.md`; absent that, the Owner is the default maintainer of
record.

### Contributors

Anyone who opens an issue, comments, or submits a pull request. No prior
approval or membership is required to contribute.

## Decision-making

- **Day-to-day changes** (bug fixes, small features, docs, dependency
  bumps): a maintainer may merge after normal PR review — no separate vote
  required.
- **Cross-cutting changes** (new engineering standard, breaking API change,
  new repository, archiving a repository): proposed as an issue or PR
  against the relevant `standards/` content in
  [`UniversalStandards/UniversalStandards`](https://github.com/UniversalStandards/UniversalStandards),
  open for comment, and decided by the Owner or by maintainer consensus if
  the Owner delegates the decision.
- **Disagreements** that can't be resolved in review are escalated to the
  Owner, who makes the final call.

## Adding a maintainer

Maintainer access is granted by the Owner, typically after a contributor
has shown sustained, good-quality contributions to a specific repository.
There is no fixed contribution count or tenure requirement — it's a
judgment call based on demonstrated reliability and understanding of the
codebase.

## Removing a maintainer

Maintainer access may be revoked by the Owner for inactivity, a Code of
Conduct violation, or at the maintainer's own request.

## Changing this document

Propose changes as a pull request against this repository
(`Universal-Standard/.github`). Since this file is an org-wide default,
changes affect every repository that doesn't override it — flag that
clearly in the PR description.
