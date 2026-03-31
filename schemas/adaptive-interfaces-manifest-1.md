# Manifest Specification (adaptive-interfaces-manifest-1)

- Status: Normative
- Layer: Specification
- Applies to: Repositories under the Adaptive Interfaces organization
- Schema Identifier: `adaptive-interfaces-manifest-1`

## 1. Purpose and Role

An **Adaptive Interfaces Manifest** is a declarative, repository-level claim card.

Its purpose is to make explicit:

- what a repository claims to be,
- what role it plays in the skill ecosystem,
- what it depends on,
- what it intentionally provides,
- what is explicitly in scope and out of scope,
- and how it should be cited.

The manifest is **human-legible**, **machine-readable**, and **reviewable**.
It enables accountability, composability, and disagreement without requiring
interpretation of repository contents.

The manifest does **not** assert correctness, truth, or endorsement.

## 2. Boundaries and Non-Goals

The Adaptive Interfaces Manifest does **not**:

- replace `README.md` documentation,
- encode build, execution, or deployment configuration,
- contain interpretive claims, observations, or conclusions,
- replace citation metadata (`CITATION.cff`),
- define skill behavior or operating procedures.

### Relationship to Other Artifacts

| Artifact        | Role                                            |
| --------------- | ----------------------------------------------- |
| `MANIFEST.toml` | Declares repository intent, scope, and role     |
| `SKILL.md`      | Defines skill behavior and operating procedures |
| `CITATION.cff`  | Defines citation metadata and attribution       |
| `DECISIONS.md`  | Records design history and rationale            |

The manifest may **reference** these artifacts but does not subsume them.

## 3. File Format and Identification

The manifest is stored as `MANIFEST.toml` at the repository root.

Each manifest **must** declare the schema identifier and URL:

```toml
schema = "adaptive-interfaces-manifest-1"
schema_url = "https://github.com/adaptive-interfaces/.github/blob/main/schemas/adaptive-interfaces-manifest-1.md"
```

These fields denote conformance to this specification document.

## 4. Attribute Definitions

### 4.1 `[meta]` - Manifest Metadata

Declares the framework context for this manifest.

| Field         | Required | Type   | Description                                     |
| ------------- | -------- | ------ | ----------------------------------------------- |
| framework     | Yes      | string | Owning framework name                           |
| framework_url | Yes      | string | URL of the owning organization or framework     |
| description   | Yes      | string | One-sentence description of the manifest's role |
| purpose       | Yes      | string | One-sentence statement of intent                |

### 4.2 `[repo]` - Repository Identity

Declares the stable identity and intent of the repository.

| Field   | Required | Type   | Description                                                                 |
| ------- | -------- | ------ | --------------------------------------------------------------------------- |
| name    | Yes      | string | Repository name                                                             |
| kind    | Yes      | string | Repository kind: `skill`, `spec`, `application`, `library`, `schema`, `lab` |
| status  | Yes      | string | Lifecycle status: `active`, `exploratory`, `deprecated`, `archived`         |
| since   | Yes      | string | Initial year of the repository                                              |
| summary | Yes      | string | One-sentence description of purpose                                         |

### 4.3 `[role]` - Ecosystem Position

Declares where the repository sits in the skill ecosystem
and how it relates to other repositories.

| Field      | Required | Type         | Description                                       |
| ---------- | -------- | ------------ | ------------------------------------------------- |
| layer      | Yes      | string       | Position: `foundational`, `domain`, `application` |
| invoked-by | Yes      | list[string] | Repositories or skills that invoke this one       |
| invokes    | Yes      | list[string] | Repositories or skills this one depends on        |

An empty list indicates no declared relationships in that direction.

**Allowed values for `role.layer`:**

| Value          | Meaning                                                         |
| -------------- | --------------------------------------------------------------- |
| `foundational` | Provides shared protocol invoked by other skills; no skill deps |
| `domain`       | Applies foundational protocol to a specific domain              |
| `application`  | End-user artifact built on domain and foundational skills       |

### 4.4 `[depends]` - Declared Dependencies

Declares upstream commitments beyond the skill ecosystem.

| Field    | Required | Type         | Description                                              |
| -------- | -------- | ------------ | -------------------------------------------------------- |
| required | Yes      | list[string] | Dependencies required to interpret or use the repository |
| optional | Yes      | list[string] | Optional tools or integrations                           |

An empty list indicates no declared dependencies.

### 4.5 `[provides]` - Intended Artifacts

Declares which artifacts are intentionally provided and maintained.

| Field     | Required | Type         | Description                                                       |
| --------- | -------- | ------------ | ----------------------------------------------------------------- |
| artifacts | Yes      | list[string] | Files or directories considered part of the repository's contract |

This section supports review, automation, and governance checks.

### 4.6 `[scope]` - Semantic Boundary

Defines what the repository explicitly includes and excludes.

| Field    | Required | Type         | Description                                          |
| -------- | -------- | ------------ | ---------------------------------------------------- |
| includes | Yes      | list[string] | In-scope concepts, behaviors, or responsibilities    |
| excludes | Yes      | list[string] | Explicitly out-of-scope concepts or responsibilities |

Scope declarations are normative and intended to prevent scope creep,
misinterpretation, and inappropriate reuse.

### 4.7 `[citation]` - Citation Pointer

Declares how the repository should be cited.

| Field     | Required | Type   | Description                                            |
| --------- | -------- | ------ | ------------------------------------------------------ |
| preferred | Yes      | string | Preferred citation target: `software`, `paper`, `spec` |

## 5. Normative Status

This document defines the **normative meaning** of
`adaptive-interfaces-manifest-1`.

Manifests claiming this schema **must** conform to the attribute definitions
and boundaries described here.

Examples are illustrative and non-normative.

## 6. Change Control

Revisions to this specification are versioned in the
[adaptive-interfaces profile](https://github.com/adaptive-interfaces/.github)
repository under `schemas/`.

Manifests should reference the schema identifier, not a mutable interpretation.
