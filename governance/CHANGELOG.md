# Changelog

All notable changes to the **career-architecture** system are documented here.

This changelog tracks **system-level changes**, not day-to-day job search activity.

For weekly execution outcomes, see `logs/weekly/`.
For decision rationale, see `adr/`.

---

## Unreleased

- (add changes here before a tagged release)

---

## 2026-02-13

### Added

- Initial repo architecture:
  - `README.md`
  - `CANON_ARCH.md`
- ADR framework:
  - `adr/README.md`
  - `adr/ADR-INDEX.md`
  - ADR-001 … ADR-006
- Governance docs:
  - `governance/PRINCIPLES.md`
  - `governance/BOUNDARIES.md`
  - `governance/RISK_REGISTER.md`
  - `governance/CHANGELOG.md`

### Notes

- Established the 3-layer model: person truth repos → shared workspace (`careers/`) → automation engine (`jobify-ai/`).
- Declared AI advisory-only and validation gates required before export.

---

## Release tags

When you cut a stable snapshot, add a git tag and record it here (example):

- `career-arch-v1.0` — 2026-02-13

