# ADR-006: Validation Requirement

- **Status:** Accepted
- **Date:** 2026-02-13

---

## Context

Resume work fails when content is not defensible or consistent:

- claims drift across variants
- ATS formatting breaks parsers
- bullets are vague or exaggerated
- facts (dates/titles/locations) conflict
- sensitive/confidential details leak into public artifacts

Because this system supports multiple people, inconsistent validation produces compounding errors.

We need a minimum validation gate that applies before exporting or using a resume in execution.

---

## Decision

A resume (general or lane variant) must pass **Validation Requirements** before it can be:

- exported to `careers/people/<name>/resume_exports/`
- used as an input to Jobify-AI for role tailoring
- sent in an application

Validation consists of three layers:

1. **Facts validation** (truth)
2. **Claim validation** (defensibility)
3. **Format validation** (ATS + consistency)

---

## Validation requirements

### 1) Facts validation (non-negotiable)

Must be consistent with the person’s `RESUME_MASTER.md`:

- employer name
- job title
- location
- start/end dates

**Rule:** lane variants may reorder or omit items, but must not contradict facts.

---

### 2) Claim validation (defensibility)

Each bullet must be defensible using at least one of:

- an internal artifact (code, doc, design note)
- a public artifact (GitHub repo, portfolio link)
- a plausible verbal explanation (what you did, how, why, and constraints)

Prohibited patterns:

- invented metrics (percentages, dollars, scale) without evidence
- exaggerated scope (“owned company-wide X”) when scope was smaller
- ambiguous claims with no action or outcome

Recommended bullet structure:

- **Action** + **object** + **constraint** + **impact**

---

### 3) Format validation (ATS + consistency)

ATS-safe minimums:

- consistent headers (Experience / Education / Skills)
- consistent date format (choose one and keep it)
- no tables for ATS variants
- simple bullets; avoid graphics and multi-column layouts
- predictable contact header formatting

Consistency checks:

- tense consistency (past vs present)
- role identity coherence (no mixed lane identity)
- no duplicate bullets that contradict each other

---

## Consequences

### Positive

- Reduces drift and interview risk.
- Improves ATS parse reliability.
- Improves credibility and consistency across variants.
- Scales across people with fewer errors.

### Trade-offs

- Adds review time before exports.
- Slows iteration if master facts are not maintained.
- Requires discipline to avoid “quick edits” in exported resumes.

---

## Alternatives considered

1. **No formal validation (trust ad-hoc review)**
   - Rejected; drift becomes inevitable.

2. **Strict evidence requirements for every claim**
   - Rejected; too slow and unrealistic for job search speed.

3. **Only ATS validation**
   - Rejected; does not prevent factual drift or exaggeration.

---

## Implementation notes

### Minimal checklist (export gate)

- Facts match the master (dates/titles/locations)
- No sensitive/confidential data
- Bullets are defensible (no invented metrics)
- ATS-safe formatting (no tables)
- Lane coherence check passed

### Where validation lives

- The canonical rules live here (ADR-006) and in `CANON_ARCH.md`.
- Operational checklists may live in:
  - `playbooks/` (execution steps)
  - `scorecards/` (weekly review)
  - `careers/docs/02_RESUME_ATS/ATS_RULES.md` (if mirrored there)

---

## Links

- ADR-001 (resume repo as human authority)
- ADR-002 (lane-based strategy)
- ADR-003 (AI advisory)
- `governance/RISK_REGISTER.md`
- `playbooks/EXECUTION_LOOP.md`

