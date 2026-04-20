# SASTER ↔ OWASP Mapping

## Overview

SASTER patterns map to both the OWASP Top 10 for LLM Applications (2025) and the OWASP Top 10 for Agentic Applications (2026). This mapping enables practitioners to score SASTER findings using OWASP frameworks and identify coverage gaps.

## Mapping Table

| SASTER | Pattern | OWASP LLM Top 10 | OWASP Agentic Top 10 |
|--------|---------|-------------------|----------------------|
| 1 | Instruction Injection | LLM01: Prompt Injection | ASI01: Agent Goal Hijack |
| 2 | Document Injection | LLM01: Prompt Injection | ASI01: Agent Goal Hijack |
| 3 | Role Hijacking | LLM01: Prompt Injection | ASI01: Agent Goal Hijack |
| 4 | Persona Override | LLM01: Prompt Injection | ASI01: Agent Goal Hijack |
| 5 | Context Window Poisoning | LLM01: Prompt Injection | ASI06: Memory & Context Poisoning |
| 6 | System Prompt Extraction | LLM07: System Prompt Leakage | ASI01: Agent Goal Hijack |
| 7 | Tool Name Disclosure | LLM07: System Prompt Leakage | ASI02: Tool Misuse & Exploitation |
| 8 | Multi-Modal Injection | LLM01: Prompt Injection | ASI01: Agent Goal Hijack |
| 9 | Serialization Attacks | LLM01: Prompt Injection | ASI02: Tool Misuse & Exploitation |
| 10 | Encoding Bypass | LLM01: Prompt Injection | ASI01: Agent Goal Hijack |
| 11 | Specification Drift | — | ASI10: Rogue Agents |
| 12 | Proxy Optimization | LLM09: Misinformation | ASI10: Rogue Agents |
| 13 | Malicious Compliance | — | ASI10: Rogue Agents |
| 14 | Gradual Intent Erosion | LLM01: Prompt Injection | ASI01: Agent Goal Hijack |
| 15 | Selective Omission | LLM09: Misinformation | ASI10: Rogue Agents |
| 16 | Confidence Miscalibration | LLM09: Misinformation | ASI09: Human-Agent Trust Exploitation |
| 17 | Intent Alteration (EFT) | — | ASI10: Rogue Agents |
| 18 | Semantic Recasting (EFT) | — | ASI10: Rogue Agents |
| 19 | Contradiction Denial (EFT) | LLM09: Misinformation | ASI10: Rogue Agents |
| 20 | Alteration Denial (EFT) | LLM09: Misinformation | ASI10: Rogue Agents |
| 21 | MCP Tool Trust Exploitation | LLM01: Prompt Injection | ASI02: Tool Misuse & Exploitation |
| 22 | Cross-Model Compositional | — | ASI07: Insecure Inter-Agent Communication |
| 23 | Self-Fulfilling Tool Belief | — | ASI02: Tool Misuse & Exploitation |
| 24 | JiTOR | — | ASI02: Tool Misuse & Exploitation |
| 25 | Resource Exhaustion (REA) | LLM10: Unbounded Consumption | ASI08: Cascading Failures |
| 26 | Recon-Gated Injection (RGI) | LLM01: Prompt Injection | ASI01: Agent Goal Hijack |
| 27 | Detection Layer Injection (DLI) | LLM01: Prompt Injection | ASI02: Tool Misuse & Exploitation |
| 28 | Salience Suppression Exfil (SSE) | LLM01: Prompt Injection | ASI01: Agent Goal Hijack |
| 29 | Stylistic Distribution Shift | LLM01: Prompt Injection | ASI01: Agent Goal Hijack |
| 30 | Temporal Anchoring | LLM09: Misinformation | ASI06: Memory & Context Poisoning |
| 31 | Compositional Capability Emergence | LLM08: Excessive Agency | ASI07: Insecure Inter-Agent Communication |

## Coverage Analysis

**SASTER patterns with no OWASP LLM mapping (unique to agent context):**
SASTER 11, 13, 17, 18, 22, 23, 24 — these behavioral and epistemic patterns are agent-specific and not covered by the LLM-focused OWASP Top 10.

**OWASP Agentic risks with limited SASTER coverage:**
ASI03 (Identity & Privilege Abuse), ASI04 (Agentic Supply Chain Vulnerabilities), ASI05 (Unexpected Code Execution), ASI09 (Human-Agent Trust Exploitation) — these are architectural and supply-chain risks rather than behavioral attack patterns. SASTER focuses on behavioral techniques; infrastructure hardening and supply chain security are complementary concerns.
