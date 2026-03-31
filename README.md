# .github

[![Link Check](https://github.com/adaptive-interfaces/.github/actions/workflows/links.yml/badge.svg?branch=main)](https://github.com/adaptive-interfaces/.github/actions/workflows/links.yml)
[![Markdown Lint](https://github.com/adaptive-interfaces/.github/actions/workflows/md-lint.yml/badge.svg?branch=main)](https://github.com/adaptive-interfaces/.github/actions/workflows/md-lint.yml)

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

| Repository                                                                                    | Kind               | Description                                                                     |
| --------------------------------------------------------------------------------------------- | ------------------ | ------------------------------------------------------------------------------- |
| [adaptive-conformance-spec](https://github.com/adaptive-interfaces/adaptive-conformance-spec) | Foundational skill | Behavioral protocol for agents working in unfamiliar codebases or tool surfaces |
| [adaptive-tool-discovery](https://github.com/adaptive-interfaces/adaptive-tool-discovery)     | Domain skill       | Learn and map the capabilities of an external tool set                          |
| [adaptive-onboarding](https://github.com/adaptive-interfaces/adaptive-onboarding)             | Domain skill       | Build team-member-level context for a specific codebase or project              |
| [adaptive-skill-lab](https://github.com/adaptive-interfaces/adaptive-skill-lab)               | Lab                | Incubator for developing, testing, and refining skills                          |

## Developer

Before pushing changes, please verify against the local `.markdownlint.json`:

```shell
npx markdownlint-cli2 --fix "**/*.md"
```
