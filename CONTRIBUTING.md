# Contributing to SASTER

SASTER is a community taxonomy. New attack patterns emerge as agent architectures evolve.

## Proposing a New Pattern

Open an issue with:
- **Pattern name** and proposed SASTER number
- **Tier classification** (1-4) with justification
- **Attack mechanism** — how the attack works
- **Detection signals** — how to identify the pattern
- **Example scenario** — at least one concrete example
- **OWASP mapping** — which OWASP categories it relates to

## Refining an Existing Pattern

Open a PR with changes to `SASTER.md`. Include reasoning for the refinement in the PR description.

## Style Guide

- Descriptions should be concrete and actionable, not theoretical
- Every pattern needs at least one real-world or realistic example
- Detection signals should be implementable by a security team
- Use neutral, professional language throughout
