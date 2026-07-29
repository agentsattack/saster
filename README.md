# SASTER — Systematic Agent Security Threat Evaluation and Rating

**v1.1 — May 2026**

A classification framework for AI agent attack patterns. 32 patterns across 4 tiers (SASTER-32 reserved) covering overt injection, behavioral manipulation, epistemic exploitation, and infrastructure attacks. Extended in v1.1 with stylistic, temporal, compositional, and reconnaissance patterns (SASTER 29, 30, 31, 33).

SASTER provides the shared vocabulary that practitioners need to describe, test for, and defend against AI agent threats. It complements OWASP's Top 10 for LLM Applications and Top 10 for Agentic Applications by providing specific, testable attack techniques rather than risk categories.

## Quick Reference

| Tier | Patterns | Focus |
|------|----------|-------|
| Tier 1: Overt Deception | SASTER 1-10 | Direct prompt injection, extraction, and encoding bypass |
| Tier 2: Correctly Wrong | SASTER 11-16, 29 | Behavioral manipulation and stylistic distribution shift |
| Tier 3: Epistemic Exploitation | SASTER 17-24, 30-31 | Tool trust, belief manipulation, temporal anchoring, and compositional capability emergence |
| Tier 4: Infrastructure & Recon | SASTER 25-28, 33 | Resource exhaustion, fingerprinting, detection evasion, and context stripping |

SASTER-32 is reserved for a candidate pattern under refinement.

## Full Taxonomy

See [SASTER.md](SASTER.md) for the complete taxonomy with descriptions, detection signals, and example scenarios.

## OWASP Mapping

See [OWASP_MAPPING.md](OWASP_MAPPING.md) for mappings between SASTER patterns and OWASP LLM Top 10 / Agentic Top 10 categories.

## Reference-implementation coverage

SASTER is implementation-independent — a pattern is defined by its attack mechanism and detection signal, not by any one tool. The table below records coverage in the open-source reference harness [`saster-harness`](https://github.com/agentsattack/saster-harness) as of v0.4.x: **13 detectors covering 9 of the 32 patterns.** The remaining 23 are specification-only (defined here, no reference detector yet). Other implementations may cover a different subset.

| # | Pattern | Tier | Detector? | Mode | Note |
|---|---|---|:---:|---|---|
| 1 | Instruction Injection | 1 | — | — | specification only |
| 2 | Document Injection | 1 | — | — | specification only |
| 3 | Role Hijacking | 1 | — | — | specification only |
| 4 | Persona Override | 1 | — | — | specification only |
| 5 | Context Window Poisoning | 1 | — | — | specification only |
| 6 | System Prompt Extraction | 1 | — | — | specification only |
| 7 | Tool Name Disclosure | 1 | — | — | specification only |
| 8 | Multi-Modal Injection | 1 | — | — | specification only |
| 9 | Serialization Attacks | 1 | — | — | specification only |
| 10 | Encoding Bypass | 1 | — | — | specification only |
| 11 | Specification Drift | 2 | ✓ | induced | induced-only — cannot run against a static corpus |
| 12 | Proxy Optimization | 2 | — | — | specification only |
| 13 | Malicious Compliance | 2 | — | — | specification only |
| 14 | Gradual Intent Erosion | 2 | ✓ | induced | induced-only — cannot run against a static corpus |
| 15 | Selective Omission | 2 | — | — | specification only |
| 16 | Confidence Miscalibration | 2 | — | — | specification only |
| 17 | Intent Alteration Without Disclosure (EFT) | 3 | — | — | specification only |
| 18 | Semantic Recasting (EFT) | 3 | ✓ | passive + induced + multi-turn | |
| 19 | Contradiction Denial (EFT) | 3 | — | — | specification only |
| 20 | Alteration Denial / Gaslighting (EFT) | 3 | — | — | specification only |
| 21 | MCP Tool Trust Exploitation | 3 | — | — | specification only |
| 22 | Cross-Model Compositional Weaponization | 3 | — | — | specification only |
| 23 | Self-Fulfilling Tool Belief | 3 | — | — | specification only |
| 24 | Just-in-Time Ontological Reframing (JiTOR) | 3 | ✓ | passive + induced | |
| 25 | Resource Exhaustion Attack (REA) | 4 | — | — | specification only |
| 26 | Recon-Gated Injection (RGI) | 4 | ✓ | passive + induced | |
| 27 | Detection Layer Injection (DLI) | 4 | ✓ | passive | |
| 28 | Salience Suppression Exfiltration (SSE) | 4 | ✓ | passive | |
| 29 | Stylistic Distribution Shift | 2 | — | — | specification only |
| 30 | Temporal Anchoring | 3 | — | — | specification only |
| 31 | Compositional Capability Emergence | 3 | ✓ | passive | |
| 32 | *(reserved)* | — | — | — | reserved; not assigned |
| 33 | Context Stripping | 4 | ✓ | passive | |

Covered set: **11, 14, 18, 24, 26, 27, 28, 31, 33**. SASTER-11 and SASTER-14 are induced-only (active live-agent probes, no passive detector) and therefore cannot run against a static/recorded corpus.

## Contributing

SASTER is a living taxonomy. Attack patterns evolve as agent architectures change. To propose a new pattern or refine an existing one, open an issue or pull request.

New pattern proposals should include: pattern name, tier classification, attack mechanism, detection signals, and at least one concrete example scenario.

## Citation

If you reference SASTER in research or publications:

> Suto, L. (2026). SASTER: Systematic Agent Security Threat Evaluation and Rating (v1.1, May 2026). https://github.com/agentsattack/saster

When citing a specific pattern, reference the version in which it appeared: e.g., SASTER-33 (v1.1).

## Author

Larry Suto — larry@stratdatsec.com

## License

CC BY 4.0 — Share and adapt with attribution.
