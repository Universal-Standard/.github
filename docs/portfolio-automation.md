# Universal Portfolio and Autonomous Remediation

This repository is the control plane for the ATLANTIS portfolio GitHub automation.

## Scope

The baseline covers ATLANTIS, SWARM, HITMAN, Universal Standards, CAROMAR, and the Universal Standard MCP Server. It replaces PR-size classification with system, area, lifecycle, dependency, agent, and review state.

## Autonomous loop

1. A new issue is classified and, unless excluded by policy, assigned to GitHub Copilot cloud agent.
2. Copilot implements the issue and opens or updates a pull request.
3. The workflow requests Copilot code review when a PR is opened, reopened, marked ready, and after every new push; existing CI, CodeQL, tests, Codex, Claude, and human reviewers may also report findings.
4. Actionable review comments from Copilot, Codex, or Claude are aggregated and deduplicated.
5. A Copilot Agent Task is started against the existing pull-request branch.
6. Every new commit invalidates verified/merge-ready state and requires a fresh review.
7. The loop repeats until a current-head review is approved or the circuit breaker stops repeated failures.
8. GitHub auto-merge is armed only after the workflow marks the current head verified and no manual-review policy label blocks automation. Native rulesets, required checks, and required reviews remain authoritative.

## Required caller files

Each participating repository should contain:

- `.github/workflows/universal-portfolio.yml`
- `.github/labeler.yml`
- `.github/agents/universal-remediation-agent.agent.md`

## Required configuration

### COPILOT_AGENT_TOKEN

A fine-grained **user** token is required for autonomous agent assignment and Agent Tasks. GitHub's Agent Tasks API is currently public preview and requires the repository **Agent tasks: read/write** permission. GitHub App installation tokens are not accepted by that endpoint.

Store the token as `COPILOT_AGENT_TOKEN` in each caller repository or through an allowed organization secret.

### PROJECTS_TOKEN

Optional. When supplied together with `PORTFOLIO_PROJECT_ID`, issues and pull requests are added to the portfolio Project and the workflow attempts to synchronize these fields when present:

- Status
- Primary System
- Area
- Repository
- Integration State

### PORTFOLIO_PROJECT_ID

Optional repository/organization variable containing the ProjectV2 node ID.

## Repository settings still required

The workflow explicitly requests Copilot code review for each eligible new PR HEAD, including after remediation pushes. Repository/organization rulesets may also enable automatic Copilot review and Review new pushes as defense in depth. Keep branch rulesets and required checks enabled. This automation never bypasses those protections.

## Manual safety gates

Any of these labels prevents fully autonomous completion:

- `agent/manual`
- `no-agent`
- `security/manual-review`
- `governance/manual-review`

The remediation circuit breaker also sets `status/agent-blocked` after the configured maximum passes or when the same normalized findings survive repeated passes.

## Supply-chain policy

External Actions are pinned to immutable full commit SHAs. Upgrades should be proposed and reviewed as dependency changes rather than floating major-version tags.
