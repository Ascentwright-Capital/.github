# .github

Defaults that every repository in Ascentwright-Capital inherits.

| Path | What it does |
|---|---|
| `pull_request_template.md` | The PR description every repo starts from, unless it has its own. |
| `.github/workflows/node-ci.yml` | Reusable CI: install, then run the scripts a repo names. Call it from a repo's own workflow. |
| `.github/workflows/harness-check.yml` | Reusable check that a repo mounts `agent-harness` as a submodule at `.agents/shared`. |
| `.github/workflows/ai-credit-check.yml` | Reusable check that fails a pull request whose title, description or commits credit an AI. |
| `.github/workflows/ai-credit.yml` | Runs that check on this repository's own pull requests. |
| `.github/workflows/pr-evidence-check.yml` | Reusable check that fails a pull request whose description does not show the change working: screenshots and a demo video, or the commands run and their output. |
| `.github/workflows/pr-evidence.yml` | Runs that check on this repository's own pull requests. |
| `.github/workflows/railway-release.yml` | Reusable release: runs the checks, then deploys each Railway service in order. A product calls it on a release tag. |
| `workflow-templates/` | Starter workflows offered under Actions → New workflow: Node CI, AI credit, PR evidence, and release to Railway. |

## Releasing a product to Railway

A product on Railway deploys staging from `main` by itself, and production from a release tag
`vYYYY.MM.DD`. To set that up in a repository:

1. Actions → New workflow → "Ascentwright release to Railway", and commit it as it is.
2. Settings → Secrets and variables → Actions: add the secret `RAILWAY_TOKEN` (a Railway project
   token for production) and the variable `RAILWAY_SERVICES` (the service names, space separated,
   the one whose pre-deploy step migrates the database first).
3. Tag `main` to release: `git tag v2027.01.07 && git push origin v2027.01.07`.
| `profile/README.md` | The org's public GitHub page. |

This repository is public, as GitHub requires for org-wide defaults. Never put a secret here.
