# .github

Defaults that every repository in Ascentwright-Capital inherits.

| Path | What it does |
|---|---|
| `pull_request_template.md` | The PR description every repo starts from, unless it has its own. |
| `.github/workflows/node-ci.yml` | Reusable CI: install, then run the scripts a repo names. Call it from a repo's own workflow. |
| `.github/workflows/harness-check.yml` | Reusable check that a repo mounts `agent-harness` as a submodule at `.agents/shared`. |
| `.github/workflows/ai-credit-check.yml` | Reusable check that fails a pull request whose title, description or commits credit an AI. |
| `.github/workflows/ai-credit.yml` | Runs that check on this repository's own pull requests. |
| `workflow-templates/` | Starter workflows offered under Actions → New workflow. |
| `profile/README.md` | The org's public GitHub page. |

This repository is public, as GitHub requires for org-wide defaults. Never put a secret here.
