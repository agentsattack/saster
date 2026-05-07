# SASTER ↔ OWASP Mapping

**Version 1.1 — May 2026**
**SASTER coverage:** patterns 1–31, 33 (SASTER-32 reserved)
**OWASP frameworks referenced:**
- OWASP Top 10 for LLM Applications 2025
- **OWASP Top 10 for Agentic Applications 2026** — Agentic Security Initiative (ASI), genai.owasp.org, December 2025
- OWASP AIVSS (AI Vulnerability Scoring System) v0.5

## Overview

SASTER patterns map to the OWASP Top 10 for LLM Applications (2025), the OWASP Top 10 for Agentic Applications 2026, and OWASP AIVSS v0.5. This mapping enables practitioners to: (1) score SASTER findings using OWASP frameworks, (2) identify which OWASP risk categories each SASTER pattern detects, and (3) see where SASTER provides behavioral detection coverage for risks the OWASP frameworks identify as architecturally important but do not provide testing methodology for.

The OWASP Top 10 for Agentic Applications 2026 (published December 2025) defines **ASI09: Human-Agent Trust Exploitation** as a distinct category covering fake explainability, alteration denial, and weaponized explainability. This is an exact behavioral match for SASTER's Tier 3 epistemic fidelity patterns (17–20). The mapping below reflects ASI09 as the primary home for those patterns.

## Mapping Table — SASTER → OWASP Agentic Top 10 2026

| SASTER | Pattern | Tier | Primary ASI | Secondary ASI |
|--------|---------|------|-------------|----------------|
| 1 | Instruction Injection | 1 | ASI01 Agent Goal Hijack | — |
| 2 | Document Injection | 1 | ASI01 Agent Goal Hijack | ASI06 Memory & Context Poisoning |
| 3 | Role Hijacking | 1 | ASI01 Agent Goal Hijack | ASI03 Identity & Privilege Abuse |
| 4 | Persona Override | 1 | ASI01 Agent Goal Hijack | ASI03 Identity & Privilege Abuse |
| 5 | Context Window Poisoning | 1 | ASI06 Memory & Context Poisoning | ASI01 Agent Goal Hijack |
| 6 | System Prompt Extraction | 1 | ASI01 Agent Goal Hijack | — |
| 7 | Tool Name Disclosure | 1 | ASI02 Tool Misuse & Exploitation | — |
| 8 | Multi-Modal Injection | 1 | ASI01 Agent Goal Hijack | — |
| 9 | Serialization Attacks | 1 | ASI02 Tool Misuse & Exploitation | ASI05 Unexpected Code Execution |
| 10 | Encoding Bypass | 1 | ASI01 Agent Goal Hijack | — |
| 11 | Specification Drift | 2 | ASI10 Rogue Agents | ASI01 Agent Goal Hijack |
| 12 | Proxy Optimization | 2 | ASI10 Rogue Agents | — |
| 13 | Malicious Compliance | 2 | ASI10 Rogue Agents | ASI09 Human-Agent Trust Exploitation |
| 14 | Gradual Intent Erosion | 2 | ASI06 Memory & Context Poisoning | ASI01 Agent Goal Hijack |
| 15 | Selective Omission | 2 | ASI09 Human-Agent Trust Exploitation | ASI10 Rogue Agents |
| 16 | Confidence Miscalibration | 2 | ASI09 Human-Agent Trust Exploitation | — |
| 17 | Intent Alteration Without Disclosure (EFT) | 3 | ASI09 Human-Agent Trust Exploitation | ASI10 Rogue Agents |
| 18 | Semantic Recasting (EFT) | 3 | ASI09 Human-Agent Trust Exploitation | ASI10 Rogue Agents |
| 19 | Contradiction Denial (EFT) | 3 | ASI09 Human-Agent Trust Exploitation | ASI10 Rogue Agents |
| 20 | Alteration Denial / Gaslighting (EFT) | 3 | ASI09 Human-Agent Trust Exploitation | ASI10 Rogue Agents |
| 21 | MCP Tool Trust Exploitation | 3 | ASI04 Agentic Supply Chain Vulnerabilities | ASI02 Tool Misuse & Exploitation |
| 22 | Cross-Model Compositional Weaponization | 3 | ASI07 Insecure Inter-Agent Communication | ASI04 Agentic Supply Chain |
| 23 | Self-Fulfilling Tool Belief | 3 | ASI02 Tool Misuse & Exploitation | ASI09 Human-Agent Trust Exploitation |
| 24 | Just-in-Time Ontological Reframing (JiTOR) | 3 | ASI02 Tool Misuse & Exploitation | ASI01 Agent Goal Hijack |
| 25 | Resource Exhaustion (REA) | 4 | ASI08 Cascading Failures | ASI02 Tool Misuse & Exploitation |
| 26 | Recon-Gated Injection (RGI) | 4 | ASI01 Agent Goal Hijack | ASI06 Memory & Context Poisoning |
| 27 | Detection Layer Injection (DLI) | 4 | ASI02 Tool Misuse & Exploitation | ASI04 Agentic Supply Chain |
| 28 | Salience Suppression Exfil (SSE) | 4 | ASI02 Tool Misuse & Exploitation | ASI01 Agent Goal Hijack |
| 29 | Stylistic Distribution Shift | 2 | ASI10 Rogue Agents | ASI09 Human-Agent Trust Exploitation |
| 30 | Temporal Anchoring | 3 | ASI06 Memory & Context Poisoning | ASI01 Agent Goal Hijack |
| 31 | Compositional Capability Emergence | 3 | ASI07 Insecure Inter-Agent Communication | ASI10 Rogue Agents |
| 32 | *Reserved* | — | — | — |
| 33 | Context Stripping | 4 | ASI06 Memory & Context Poisoning | ASI09 Human-Agent Trust Exploitation |

## Coverage Analysis Against OWASP Agentic Top 10 2026

| ASI | Title | SASTER Coverage | Patterns |
|-----|-------|-----------------|----------|
| ASI01 | Agent Goal Hijack | Strong | 1, 2, 3, 4, 6, 8, 10, 11, 14, 24, 26, 28, 30 |
| ASI02 | Tool Misuse & Exploitation | Strong | 7, 9, 21, 23, 24, 25, 27, 28 |
| ASI03 | Identity & Privilege Abuse | Partial (architectural risk) | 3, 4 (secondary) |
| ASI04 | Agentic Supply Chain Vulnerabilities | Partial (tool-descriptor surface) | 21, 22, 27 |
| ASI05 | Unexpected Code Execution (RCE) | Minimal (architectural risk) | 9 (secondary) |
| ASI06 | Memory & Context Poisoning | Strong | 2, 5, 14, 26, 30, 33 |
| ASI07 | Insecure Inter-Agent Communication | Partial | 22, 31 |
| ASI08 | Cascading Failures | Direct match | 25 |
| ASI09 | Human-Agent Trust Exploitation | Strong — primary lane | 13, 15, 16, 17, 18, 19, 20, 23, 29, 33 |
| ASI10 | Rogue Agents | Strong | 11, 12, 13, 15, 17–20, 29, 31 |

## What SASTER Adds Beyond OWASP Agentic Top 10 2026

The OWASP Agentic Top 10 2026 is an awareness and architectural framework. It identifies risk categories and provides prevention guidelines. It does not specify how to test for a given category. SASTER provides the detection methodology layer:

1. **ASI09 (Human-Agent Trust Exploitation) detection.** OWASP describes "fake explainability," "weaponized explainability," and "clinical decision manipulation" as scenarios but provides no testing approach. SASTER patterns 17–20 (the EFT family) provide concrete probe-and-detect methodology with measurable behavioral signatures. SASTER-13, -15, and -16 extend coverage of this category.

2. **ASI10 (Rogue Agents) behavioral signatures.** OWASP describes rogue agents as "behavioral divergence" and lists scenarios. SASTER patterns 11, 12, 13, 15, 29 give specific drift signatures with detection harness implementations.

3. **ASI06 (Memory & Context Poisoning) progression detection.** OWASP describes the category. SASTER-14 (Gradual Intent Erosion), SASTER-30 (Temporal Anchoring), and SASTER-33 (Context Stripping) provide detectable signatures for in-session memory and context attacks.

4. **Compositional and cross-model risks.** OWASP ASI07 covers inter-agent communication broadly. SASTER-22 (Cross-Model Compositional Weaponization) and SASTER-31 (Compositional Capability Emergence) provide specific detection patterns for capability emergence across model boundaries.

5. **Reconnaissance-phase detection.** OWASP does not separately address recon as an attack stage. SASTER Tier 4 (25, 26, 27, 28, 33) provides reconnaissance-phase detection signatures observed in active engagements.

## Gaps in SASTER vs OWASP Agentic Top 10 2026

SASTER is a behavioral taxonomy. It does not currently provide patterns for the OWASP entries that are primarily architectural or infrastructure in nature:

- **ASI03 (Identity & Privilege Abuse).** Architectural — token binding, scoped credentials, OAuth intent capsules. Identity-level controls are properly an IAM concern.
- **ASI04 (Agentic Supply Chain Vulnerabilities).** SASTER-21/22/27 cover the runtime tool-descriptor surface (tool poisoning, descriptor injection). Static supply-chain risks (poisoned npm packages, compromised model weights) are out of scope for a behavioral taxonomy and properly belong to SBOM/AIBOM frameworks.
- **ASI05 (Unexpected Code Execution / RCE).** Primarily an architectural concern (sandbox, eval restrictions). SASTER-9 (Serialization Attacks) is the closest behavioral analog.

These gaps are intentional. SASTER is the behavioral detection complement to OWASP's architectural prevention guidance. Practitioners should use both: OWASP for prevention controls, SASTER for runtime detection.

## Mapping to OWASP LLM Top 10 (2025)

| OWASP LLM | SASTER Patterns |
|-----------|-----------------|
| LLM01: Prompt Injection | 1, 2, 3, 4, 5, 8, 10, 14, 21, 26, 27, 28 |
| LLM02: Sensitive Information Disclosure | (downstream impact of multiple patterns) |
| LLM03: Supply Chain | (architectural — see ASI04 gap above) |
| LLM04: Data and Model Poisoning | (training-time, out of scope for runtime SASTER) |
| LLM05: Improper Output Handling | (consumer-side, out of scope) |
| LLM06: Excessive Agency | (architectural — see ASI02/ASI03) |
| LLM07: System Prompt Leakage | 6, 7 |
| LLM08: Vector & Embedding Weaknesses | (RAG-layer, partial overlap with SASTER-2/5) |
| LLM09: Misinformation | 12, 15, 16, 19, 20 |
| LLM10: Unbounded Consumption | 25 |

## Mapping to OWASP AIVSS v0.5

AIVSS provides scoring; SASTER provides the test patterns that produce findings AIVSS scores. Highest-severity overlaps:

- **AIVSS Core Risk 1 (Tool Misuse, 8.7):** SASTER 7, 9, 21, 23, 24, 25, 27, 28
- **AIVSS Core Risk 2 (Access Control Violation, 8.1):** SASTER 6
- **AIVSS Core Risk 3 (Cascading Failures, 7.8):** SASTER 25
- **AIVSS Behavioral Integrity / Compliance Violations (ASI10):** SASTER 11, 12, 13, 15, 17–20, 29

## Citing This Mapping

> SASTER ↔ OWASP Mapping v1.1, May 2026. Maps the 32-pattern Saster Adversarial Spec & Test Evaluation Reference taxonomy (SASTER-32 reserved) to the OWASP Top 10 for LLM Applications (2025), the OWASP Top 10 for Agentic Applications 2026 (December 2025), and OWASP AIVSS v0.5.
