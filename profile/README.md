# Adaptive Interfaces

Adaptive Interfaces is an open framework
for designing how intelligent systems
interact with complex environments.

This work focuses on the interface layer,
the boundary where knowledge, capability, and
intent are exchanged between:

- humans and AI systems
- AI systems and codebases
- AI systems and tools (APIs, CLIs, services)
- AI systems and other AI systems

## Start Here

**→ [adaptive-guide](https://github.com/adaptive-interfaces/adaptive-guide)**

When agent output is technically correct
but wrong for your team,
the guide explains why and what to do about it.

It is not a tutorial.
It is an engineering discipline guide:
how to write the necessary priors,
how to write the context agents need,
and how to evaluate whether it is working.

## Core Idea

Intelligent systems act within environments that have:

- existing structure
- implicit conventions
- explicit constraints
- domain-specific expectations

Correct behavior is a function of
alignment with the environment
through which capability is applied.

Adaptive Interfaces focuses on how systems:

- infer the structure of an environment
- adapt to its constraints and patterns
- act in ways consistent with local expectations

## Repositories

| Repository                                                                                                      | Kind               | Description                                                                     |
| --------------------------------------------------------------------------------------------------------------- | ------------------ | ------------------------------------------------------------------------------- |
| [adaptive-guide](https://github.com/adaptive-interfaces/adaptive-guide)                                         | Guide              | > How to structure agent context for team-conforming output                     |
| [adaptive-conformance-specification](https://github.com/adaptive-interfaces/adaptive-conformance-specification) | Foundational skill | Behavioral protocol for agents working in unfamiliar codebases or tool surfaces |
| [adaptive-tool-discovery](https://github.com/adaptive-interfaces/adaptive-tool-discovery)                       | Domain skill       | Learn and map the capabilities of an external tool set                          |
| [adaptive-onboarding](https://github.com/adaptive-interfaces/adaptive-onboarding)                               | Domain skill       | Build team-member-level context for a specific codebase or project              |
| [adaptive-sensor-testing](https://github.com/adaptive-interfaces/adaptive-sensor-testing)                       | Worked example     | Complete example: sensor data testing using all three priors                    |
| [adaptive-skill-lab](https://github.com/adaptive-interfaces/adaptive-skill-lab)                                 | Lab                | Incubator for developing, testing, and refining skills                          |

## Reading Order

```text
adaptive-guide                      #  start here
adaptive-conformance-specification  #  foundational behavior (ACS)
adaptive-tool-discovery             #  map available tools (ATD)
adaptive-onboarding                 #  capture team conventions (AO)
adaptive-sensor-testing             #  see a complete worked example
adaptive-skill-lab                  #  build and test your skills
```

## Scope

This project focuses on intelligent systems
interacting with existing systems.

Key areas include:

### Environment Inference

- Codebase capability inference
- Engineering pattern inference
- Interface surface modeling

### Behavior Specification

- Skills and task definitions
- Constraints and boundaries
- Decision discipline

### Adaptation

- Entering and aligning to new environments
- Pattern alignment and constraint adherence
- Handling ambiguity and conflicting signals

### Evaluation

- Measuring behavioral correctness
- Assessing alignment with local engineering practices
- Reproducibility and accountability

## The Key Distinction

A prompt template tells an agent what to say.
A skill specification tells an agent how to think
and what evidence to require before acting.

Engineers who write skills rather than templates
produce agents that are reliable across novel situations —
not just the situations the template anticipated.

## Non-Goals

This project is:

- Not prompt engineering
- Not tied to a specific model or vendor
- Not a wrapper around existing APIs
- Not limited to any specific class of AI system

While current work focuses on modern AI systems
including LLM-based agents,
the framework is model-agnostic and durable.

## Direction

Adaptive Interfaces establishes:

- structured methods for environment-aware AI behavior
- reusable specifications for agent interaction
- evaluation frameworks for behavioral correctness
- a shared foundation for adaptive systems engineering

## Status

Early-stage, specification-first.
Skills are MIT licensed and designed to be forked and tuned
for specific needs.
