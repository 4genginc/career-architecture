# Boundaries

This document defines **what belongs where** and what is allowed to cross boundaries.

It exists to prevent:

- identity mixing across people
- resume drift across copies
- accidental publication of sensitive/confidential information
- tooling repos becoming “truth”

---

## Boundary 1 — Person truth vs shared work

### Person truth (restricted)

**Home:** person-level resume repos (recommended):

- `resume-rongjun/`
- `resume-mingjun/`
- `resume-weijie/`

**Contains:**

- `RESUME_MASTER.md` (authoritative bullet bank)
- facts anchors (dates, titles, certifications)
- lane variants derived from the master

**Rules:**

- owner-controlled edits only
- other people may suggest, but the owner approves
- do not publish sensitive personal information

---

### Shared workspace (collaborative)

**Home:** `careers/`

**Contains:**

- shared playbooks, templates, ATS rules
- per-person exports (non-sensitive)
- interview prep notes (sanitized)

**Rules:**

- may include generated artifacts
- must not become the authoritative source of personal truth

---

## Boundary 2 — Automation vs authority

### Automation engine

**Home:** `jobify-ai/`

**Contains:**

- code, prompts, contracts
- generation workflows
- output format definitions

**Rules:**

- AI output is advisory
- never overwrite `RESUME_MASTER.md`
- outputs must be traceable to a human source

(See ADR-003.)

---

## Boundary 3 — Public vs private

### Public-safe

OK to publish (GitHub, LinkedIn, portfolio):

- process docs (templates, playbooks)
- sanitized resume variants
- project narratives that do not reveal confidential employer details
- public demos and portfolio links

### Private-only

Do **not** publish:

- addresses, DOB, SSN, immigration/medical/financial data
- employer confidential/internal information
- private HR disputes or performance issues
- any customer-specific confidential details

---

## Boundary 4 — Identity isolation across people

### Shareable

- structure, templates, playbooks
- lane definitions, keyword sets
- phrasing patterns

### Not shareable by default

- personal achievements and impact claims
- metrics and scope numbers
- proprietary project details

**Rule:** never copy a bullet between people without explicit owner review.

---

## Boundary 5 — Where decisions live

- decisions affecting system behavior → ADRs (`adr/`)
- operational changes and weekly outcomes → logs (`logs/`)
- untested ideas → experiments (`experiments/`)
- stable truth → `CANON_ARCH.md`

---

## Quick checklist (before publishing/export)

- contains no sensitive personal data
- contains no confidential employer/customer details
- facts match the person master
- lane identity is coherent
- output is ATS-safe (if ATS variant)

---

## Links

- `CANON_ARCH.md`
- ADR-001 (human authority)
- ADR-003 (AI advisory)
- ADR-005 (collaboration boundary)
- A