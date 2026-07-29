# SASTER roadmap

Planned but not-yet-implemented changes to the taxonomy. Nothing here is
in effect; the current spec is [SASTER.md](SASTER.md).

## Deferred — Detection field revision (v1.2)

**Status:** deferred, not started. Deferred out of the OWASP-readiness
pass because it is a coordinated two-repo release, not a documentation
edit (see "Why this is its own release" below).

**Goal.** Make each pattern's `Detection:` field *falsifiable but
implementation-independent*. Today the field is descriptive prose. It
should instead name three things:

1. **The observable** — what signal is looked at.
2. **The comparison** — what is compared against what.
3. **The scope class** — one of: single-turn / windowed /
   session-baseline / cross-turn / graph / cross-session.

No thresholds, no library names, no harness-specific parameters. Concrete
thresholds are an implementation concern and live in the reference
harness's docs, not in the vendor-neutral taxonomy.

**Why not "the detector's actual decision criterion".** An earlier draft
of this item proposed replacing the prose with saster-harness's actual
decision criterion. That was rejected: it would hardcode one
implementation's thresholds into a taxonomy pitched as vendor-neutral and
make any other conformant implementation non-conformant by construction.
The scope-class abstraction keeps the field testable without binding it
to a tool.

**Conformance check (harness side).** Once the taxonomy declares a scope
class per pattern, `saster-harness`'s taxonomy-sync guard
(`tests/test_taxonomy_sync.py`) should additionally assert that every
shipped detector declares a scope class matching its pattern's declared
scope class — the same shape of guard that already enforces id / name /
tier / canonical-definition sync.

**Why this is its own release.** The harness guard pins a checksum of
`SASTER.md` and asserts each detector docstring quotes Attack / Detection
/ Example verbatim. Rewriting `Detection:` for the nine covered patterns
invalidates nine docstrings plus the pin simultaneously. That is a
coordinated taxonomy-v1.2 + harness release, sequenced as:

1. Edit the taxonomy (`Detection:` fields → observable + comparison +
   scope class; mark uncovered patterns as spec-only where useful).
2. Tag the taxonomy release.
3. Refresh the harness's vendored copy + checksum + pinned commit ref.
4. Update all 13 detector docstrings to quote the new `Detection:` text.
5. Re-run the guard until green.
