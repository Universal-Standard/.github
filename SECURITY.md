# Security Policy

This is the organization-wide default security policy for `Universal-Standard`
repositories. It applies to any repository that does not define its own
`SECURITY.md`.

## Reporting a Vulnerability

**Do not open a public GitHub issue for a security vulnerability.**

Report it privately using one of the following, in order of preference:

1. **GitHub Private Vulnerability Reporting** — on the affected repository,
   go to the **Security** tab → **Report a vulnerability**. This creates a
   private advisory visible only to maintainers and lets you collaborate on
   a fix before public disclosure.
2. **Email** — if the repository does not have private reporting enabled,
   email **philip.cotton@spurs.agency** with:
   - A description of the vulnerability and its potential impact
   - Steps to reproduce (proof-of-concept code or a minimal repro is
     extremely helpful)
   - The affected repository, file(s), and commit/version
   - Whether you believe the issue is already publicly known or exploited

## What to expect

| Stage | Target timeline |
|---|---|
| Acknowledgment of your report | Within 3 business days |
| Initial assessment (severity, affected repos) | Within 7 business days |
| Fix or mitigation plan communicated to reporter | Within 30 days for high/critical severity |
| Public disclosure | Coordinated with the reporter, typically after a fix is released |

These are targets, not contractual SLAs — actual timelines depend on
severity and complexity.

## Supported versions

Unless a specific repository's own `SECURITY.md` states otherwise, only the
latest release (or the `main`/default branch, for repositories without
tagged releases) is supported with security fixes.

## Scope

This policy covers vulnerabilities in code, configuration, and
infrastructure-as-code maintained in `Universal-Standard` repositories. It
does not cover:

- Vulnerabilities in third-party dependencies (report those upstream; we
  will still take a dependency-bump fix as a contribution)
- Social engineering or physical security issues
- Denial-of-service reports based purely on load/rate, without a specific
  exploitable flaw

## Recognition

With the reporter's consent, we credit valid reports in the relevant
release notes or security advisory.
