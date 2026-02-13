# ADR-005: Collaboration Boundary

- **Status:** Accepted
- **Date:** 2026-02-13

---

## Context

This career system supports multiple people (Rongjun, Mingjun, and later Weijie). Collaboration creates leverage, but it also introduces risks:

- mixing identities (bullets or facts crossing between people)
- accidental disclosure of sensitive personal data
- accidental disclosure of confidential employer information
- over-sharing in public repos (GitHub) that should remain private

We need explicit boundaries for:

- what can be shared across people
- what can be published publicly
- what must remain private and person-owned

---

## Decision

### 1) Two collaboration zones

**Zone A — Company-level shared knowledge (shareable)**

Allowed to share and co-edit:

- templates (resume formats, outreach templates)
- playbooks (triage, interview prep, negotiation)
- lane definitions and keyword sets
- scorecards and metrics
- ADRs and governance docs
- sanitized portfolio narratives

**Zone B — Person-level truth (restricted)**

Each person owns their truth repo and controls edits:

- `RESUME_MASTER.md`
- verified facts (dates, titles, certifications)
- personal narrative/summary choices

Other people may suggest changes, but the owner must approve.

---

### 2) Public vs private publishing

**Public-safe (OK for GitHub):**

- general process docs and templates
- non-sensitive resume variants (sanitized)
- portfolio artifacts that do not reveal confidential details

**Private-only (must not be published):**

- addresses, DOB, SSN, immigration/medical/financial records
- employer-confidential information
- internal HR disputes or performance details
- anything that would create personal or legal risk

---

### 3) Identity isolation rule

- Never copy bullets between people without explicit review.
- Never reuse “impact claims” across people.
- Share *structure and phrasing patterns*, not personal achievements.

---

### 4) Review requirement for exports

Before exporting a resume to a shared folder or public repo:

- the owner confirms the content is defensible and non-sensitive
- a second person may do a lightweight check for accidental leakage

---

## Consequences

### Positive

- Enables collaboration without mixing identities.
- Reduces risk of accidental disclosure.
- Keeps public repos clean and defensible.
- Clarifies which documents are safe to share.

### Trade-offs

- Adds review overhead when sharing/exporting.
- Slower cross-editing of personal resumes.
- Requires discipline to keep private data out of public repos.

---

## Alternatives considered

1. **No collaboration; fully isolated work**
   - Rejected; loses leverage and shared learning.

2. **Fully shared repos for everything**
   - Rejected; high risk of identity mixing and sensitive leakage.

3. **Ad-hoc sharing without documented boundaries**
   - Rejected; boundaries drift and errors happen.

---

## Implementation notes

- Put shared docs in this repo (`career-architecture/`) and/or `careers/docs/`.
- Keep person truth in person repos (`resume-<name>/`).
- Use `careers/people/<name>/resume_exports/` for publishable exports.
- If public publishing is intended, add a short “public visibility check” step to the export workflow.

---

## Links

- ADR-001 (resume repo as human authority)
- ADR-006 (validation requirements)
- `governance/BOUNDARIES.md`
- `CANON_ARCH.md`
