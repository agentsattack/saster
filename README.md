# SASTER — Systematic Agent Security Threat Evaluation and Rating

A classification framework for AI agent attack patterns. 31 patterns across 4 tiers covering overt injection, behavioral manipulation, epistemic exploitation, and infrastructure attacks.

SASTER provides the shared vocabulary that practitioners need to describe, test for, and defend against AI agent threats. It complements OWASP's Top 10 for LLM Applications and Top 10 for Agentic Applications by providing specific, testable attack techniques rather than risk categories.

## Quick Reference

| Tier | Patterns | Focus |
|------|----------|-------|
| Tier 1: Overt Deception | SASTER 1-10, 29 | Direct prompt injection and extraction |
| Tier 2: Correctly Wrong | SASTER 11-16, 30 | Behavioral manipulation producing harmful-but-compliant outputs |
| Tier 3: Epistemic Exploitation | SASTER 17-24, 31 | Tool trust, belief manipulation, and ontological attacks |
| Tier 4: Infrastructure & Recon | SASTER 25-28 | Resource exhaustion, fingerprinting, detection evasion |

## Full Taxonomy

See [SASTER.md](SASTER.md) for the complete taxonomy with descriptions, detection signals, and example scenarios.

## OWASP Mapping

See [OWASP_MAPPING.md](OWASP_MAPPING.md) for mappings between SASTER patterns and OWASP LLM Top 10 / Agentic Top 10 categories.

## Contributing

SASTER is a living taxonomy. Attack patterns evolve as agent architectures change. To propose a new pattern or refine an existing one, open an issue or pull request.

New pattern proposals should include: pattern name, tier classification, attack mechanism, detection signals, and at least one concrete example scenario.

## Citation

If you reference SASTER in research or publications:

> Suto, L. (2026). SASTER: Systematic Agent Security Threat Evaluation and Rating. https://github.com/agentsattack/saster

## Author

Larry Suto — larry@stratdatsec.com

## License

CC BY 4.0 — Share and adapt with attribution.
