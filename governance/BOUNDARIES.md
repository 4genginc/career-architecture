# Boundaries

This document defines **what belongs where** and what is allowed to cross boundaries.

It exists to prevent:

* identity mixing across people
* resume drift across copies
* accidental publication of sensitive or confidential information
* tooling repos becoming “truth”

---

## Definitions

* **Person truth:** authoritative, owner-controlled resume source-of-truth for one person.
* **Shared workspace:** collaborative space for exports and shared assets (sanitized).
* **Automation engine:** code and prompts that generate drafts/exports; never truth.
* **Public repo:** content safe to publish. Assume anything here may be shared publicly.
* **Private ops repo:** execution logs and notes that must not be published.

---

## Boundary 1 — Person truth vs shared workspace

### Person truth (restricted)

**Home:** person-level resume repos (one repo per person):

* `resume-<person>/`

**Contains:**

* `RESUME_MASTER.md` (authoritative bullet bank)
* fact anchors (dates, titles, certifications)
* lane variants derived from the master

**Rules:**

* owner-controlled edits only
* others may suggest; the owner approves
* do not store sensitive personal information
* update the master first; then regenerate/update variants

### Shared workspace (collaborative)

**Home:** `careers/`

**Contains:**

* shared playbooks, templates, ATS rules
* per-person exports (non-sensitive)
* interview prep notes (sanitized)

**Rules:**

* may include generated artifacts
* must not become the authoritative source of personal truth
* exports must be traceable back to person truth
* if the workspace is public-facing, it must follow the same “public-safe” rules below

---

## Boundary 2 — Automation vs authority

### Automation engine

**Home:** `jobify-ai/`

**Contains:**

* code, prompts, contracts
* generation workflows
* output format definitions

**Rules:**

* AI output is advisory
* never overwrite or auto-edit `RESUME_MASTER.md`
* outputs are drafts until accepted by a human
* outputs must be traceable to a human source

(See ADR-003.)

---

## Boundary 3 — Public vs private

### Public-safe (OK to publish)

OK to publish (GitHub / portfolio):

* process docs (templates, playbooks, scorecards)
* governance docs (principles, boundaries, risk register)
* experiments (without personal data)
* role positioning guidance and generic lane definitions
* portfolio links and demos that do not reveal confidential employer/customer details

**Rule:** if a file is in a public repo, it must be safe to publish without additional filtering.

### Private-only (do not publish)

Do **not** publish:

* addresses, DOB, SSN, immigration/medical/financial data
* employer confidential/internal information
* private HR disputes or performance issues
* customer-specific confidential details
* outreach logs, interview notes, informational interviews

**Private ops home:** `career-ops-private/`

* logs path: `career-ops-private/logs/`

  * `weekly/YYYY-W##.md`
  * `decisions/YYYY-MM.md`
  * `conversations/` (e.g., recruiter threads, informational interviews)

---

## Boundary 4 — Identity isolation across people

### Shareable

* structure, templates, playbooks
* lane definitions and keyword sets
* phrasing patterns

### Not shareable by default

* personal achievements and impact claims
* metrics and scope numbers
* proprietary project details

**Rule:** never copy a bullet between people without explicit owner review.

---

## Boundary 5 — Where decisions live

* decisions affecting system behavior → ADRs (`adr/`)
* untested ideas → experiments (`experiments/`)
* stable truth → `CANON_ARCH.md`
* operational changes and weekly outcomes → private logs (`career-ops-private/logs/`)

---

## Quick checklist (before publishing/export)

* contains no sensitive personal data
* contains no confidential employer/customer details
* facts match the person master
* lane identity is coherent
* output is ATS-safe (if ATS variant)

---

## Links

* `CANON_ARCH.md`
* ADR-001 (human authority)
* ADR-003 (AI advisory)
* ADR-005 (collaboration boundary)
