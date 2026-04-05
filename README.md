# .github

[![Version](https://img.shields.io/badge/version-v0.2.2-blue)](https://github.com/adaptive-interfaces/.github/releases)
[![License: MIT](https://img.shields.io/badge/license-MIT-green.svg)](https://opensource.org/license/MIT)
[![CI](https://github.com/adaptive-interfaces/.github/actions/workflows/ci-org.yml/badge.svg?branch=main)](https://github.com/adaptive-interfaces/.github/actions/workflows/ci-org.yml)
[![Markdown Lint](https://github.com/adaptive-interfaces/.github/actions/workflows/md-lint.yml/badge.svg?branch=main)](https://github.com/adaptive-interfaces/.github/actions/workflows/md-lint.yml)
[![Check Links](https://github.com/adaptive-interfaces/.github/actions/workflows/links.yml/badge.svg?branch=main)](https://github.com/adaptive-interfaces/.github/actions/workflows/links.yml)
[![Dependabot](https://img.shields.io/badge/Dependabot-enabled-brightgreen.svg)](https://github.com/adaptive-interfaces/.github/security)

Organization profile and shared infrastructure for
[Adaptive Interfaces](https://github.com/adaptive-interfaces).

## Profile

[`profile/README.md`](./profile/README.md):
the organization profile displayed on the Adaptive Interfaces GitHub page.

## Schemas

Normative specifications for shared file formats used across all
Adaptive Interfaces repositories.

| Schema                                                                                     | Description                                                                                |
| ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ |
| [`schemas/adaptive-interfaces-manifest-1.md`](./schemas/adaptive-interfaces-manifest-1.md) | Specification for `MANIFEST.toml`, the declarative claim card required in every repository |

Each repository in the `adaptive-interfaces` organization includes a
`MANIFEST.toml` at its root that declares conformance to the manifest schema.

## Repositories

| Repository                                                                                                      | Kind               | Description                                                                     |
| --------------------------------------------------------------------------------------------------------------- | ------------------ | ------------------------------------------------------------------------------- |
| [adaptive-conformance-specification](https://github.com/adaptive-interfaces/adaptive-conformance-specification) | Foundational skill | Behavioral protocol for agents working in unfamiliar codebases or tool surfaces |
| [adaptive-tool-discovery](https://github.com/adaptive-interfaces/adaptive-tool-discovery)                       | Domain skill       | Learn and map the capabilities of an external tool set                          |
| [adaptive-onboarding](https://github.com/adaptive-interfaces/adaptive-onboarding)                               | Domain skill       | Build team-member-level context for a specific codebase or project              |
| [adaptive-skill-lab](https://github.com/adaptive-interfaces/adaptive-skill-lab)                                 | Lab                | Incubator for developing, testing, and refining skills                          |

## Developer

Before pushing changes, please verify against the local `.markdownlint.json`:

```shell
npx markdownlint-cli2 --fix "**/*.md" "!**/.venv/**"
```

## Organization Checks

You need a GitHub Personal Access Token (PAT)
with read access to the org.
And it must be set as an environment variable before running the script.

### Step 1. Create the token

Go to <https://github.com/settings/tokens?type=beta> (fine-grained tokens, recommended)

- Resource owner: adaptive-interfaces (the org)
- Repository access: All repositories
- Permissions needed:
  - Actions = Read-only
  - Contents = Read-only
  - Metadata = Read-only (auto-selected)

### Step 2. Generate and Copy the token

Copy to .env (not committed to GitHub).
You only see it once.

## Command Reference

The commands below are used in the workflow guide above.
They are provided here for convenience.

Follow the guide for the **full instructions**.

<details>
<summary>Show command reference</summary>

### In a machine terminal (open in your `Repos` folder)

After you get a copy of this repo in your own GitHub account,
open a machine terminal in your `Repos` folder:

```shell
# Replace username with YOUR GitHub username.
git clone https://github.com/username/.github

cd .github
code .
```

### In a VS Code terminal

```shell
uv self update
uv python pin 3.14
uv sync --extra dev --extra docs --upgrade
uvx pre-commit install

git add -A
uvx pre-commit run --all-files
# repeat if changes were made
git add -A
uvx pre-commit run --all-files

# just console / console and md file
uv run --env-file .env python src/adaptive_interfaces_github/checks.py
uv run --env-file .env python src/adaptive_interfaces_github/checks.py --write-markdown org-health.md

uv run ruff format .
uv run ruff check . --fix
uv run zensical build

git add -A
git commit -m "update"
git push -u origin main
```

</details>

## Resources

- [Pro-Analytics-02](https://denisecase.github.io/pro-analytics-02/) - guide to professional Python

## Annotations

[ANNOTATIONS.md](./ANNOTATIONS.md)

<!--
WHY: Keep decision rationale close to code and configuration.
-->

## License

[MIT](./LICENSE)

<!--
WHY: Provide terms of reuse and limits of liability.
-->
