# SASTER Changelog

All notable changes to the SASTER taxonomy are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), and this project adheres to semantic versioning for taxonomies: major versions for tier structure changes, minor versions for new patterns, patch versions for clarifications and corrections.

## [1.1] — 2026-05-06

### Added
- SASTER-29: Stylistic Distribution Shift (Tier 2 Correctly Wrong)
- SASTER-30: Temporal Anchoring (Tier 3 Epistemic Exploitation)
- SASTER-31: Compositional Capability Emergence (Tier 3 Epistemic Exploitation)
- SASTER-33: Context Stripping (Tier 4 Infrastructure & Reconnaissance)
- CHANGELOG.md introduced as the canonical record of taxonomy evolution
- OWASP_MAPPING.md gap analysis section identifying ASI03/ASI04/ASI05 as architectural categories where SASTER intentionally provides minimal coverage
- SASTER-29 prior art citation: Bisconti et al. adversarial poetry research (arXiv 2511.15304, 2026)
- SASTER-31 prior art citation: Anthropic Cunningham et al. CC++ paper (arXiv 2601.04603, 2026), describing related reconstruction attacks

### Changed
- OWASP_MAPPING.md: full refresh against the officially published OWASP Top 10 for Agentic Applications 2026 (genai.owasp.org, December 2025)
- OWASP_MAPPING.md: SASTER-17/18/19/20 (the EFT cluster) mapped to ASI09 Human-Agent Trust Exploitation, matching the explicit scope of that 2026 category (fake explainability, alteration denial, weaponized explainability)
- SASTER.md: version header bumped to v1.1
- SASTER.md: tier headers updated to reflect new pattern membership (Tier 2: 11-16, 29; Tier 3: 17-24, 30-31; Tier 4: 25-28, 33)
- SASTER.md: SASTER-30 description sharpened to specifically describe self-attributed false temporal anchors (e.g. "you told me yesterday") rather than generic false temporal claims, matching the pattern's empirical detection signature
- SASTER.md: SASTER-31 description and detection signature aligned with bridge-variable / manifest-review detection mechanism used in practice
- SASTER.md: Extensions section removed; new patterns integrated into tier homes
- README.md: pattern count updated to "32 patterns across 4 tiers (SASTER-32 reserved)"
- README.md: citation version-locked to v1.1

### Reserved
- SASTER-32: reserved for a candidate pattern under refinement. Intentionally skipped in v1.1; not available for assignment to other patterns.

### Notes
- Tier structure unchanged from v1.0 (4 tiers).
- SASTER-31 is closely related to SASTER-22 but distinguished: -22 targets chained generation across models; -31 targets chained execution across tools or agents. Both can co-occur in the same attack.
- SASTER-33 commonly co-occurs with SASTER-22 and SASTER-26 during active reconnaissance. Layered detection across these patterns has been validated against live attack traffic.
- SASTER-33 was placed in Tier 4 (Infrastructure & Reconnaissance) rather than Tier 3 because its empirical detection signature in active engagements is reconnaissance-flavored, even though the underlying attack class has an epistemic dimension.
- v1.1 is the first release with a formal CHANGELOG. Prior 28-pattern published state is recorded as v1.0 below for historical reference; no v1.0 git tag was created at the time.

## [1.0] — 2026-04 (historical, not git-tagged)

### Added
- Initial public release of the SASTER taxonomy.
- 28 patterns across 4 tiers: Overt Deception (1-10), Correctly Wrong (11-16), Epistemic Exploitation (17-24), Infrastructure & Reconnaissance (25-28).
- OWASP LLM Top 10 (2025) mappings.
- OWASP Agentic Top 10 mappings (pre-2026 draft scheme).
- Prior art citations: HiddenLayer Policy Puppetry (SASTER-9, -27), HiddenLayer EchoGram (SASTER-27), Anthropic Constitutional Classifiers referenced as defense baseline (SASTER-27).
- Original contributions: EFT pattern cluster (SASTER-17 through -20), JiTOR (SASTER-24).
