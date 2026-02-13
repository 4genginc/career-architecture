# EXP-001: Resume A/B Tests

- **Status:** Active
- **Owner:** 4G-ENG Careers
- **Start date:** 2026-02-13
- **Lane:** (Backend / Embedded / AI Platform / UIUX)

---

## Hypothesis

A controlled resume change (headline/summary/skills/bullet selection) will improve at least one of:

- response rate
- screen rate
- quality of outreach replies

without increasing validation risk (ADR-006).

---

## What is being tested

Choose one test type per run:

### A) Summary and headline

- Variant A: current summary
- Variant B: rewritten summary emphasizing top 2 lane signals

### B) Skills block ordering

- Variant A: current skill ordering
- Variant B: reorder to match JD keywords (no new claims)

### C) Bullet selection and ordering

- Variant A: current bullets
- Variant B: swap in 2–4 higher-signal bullets from the master

### D) Formatting (ATS-safe)

- Variant A: current ATS format
- Variant B: simplified headings/spacing for parsing stability

---

## Experimental design

### Variants

- **A:** (describe)
- **B:** (describe)

### Population

- Target roles: (role family)
- Companies: (optional)
- Channels: (applications / outreach-first)

### Sample size guidance

- Minimum: **10 submissions** per variant (if possible)
- Better: **20+** per variant

If volume is low, extend duration and keep the test narrow.

---

## Measurement

Track per variant:

- submissions count
- responses count
- screens scheduled
- time-to-first-response (optional)
- qualitative recruiter feedback (if any)

Record in weekly logs:

- `career-ops-private/logs/weekly/YYYY-W##.md`

---

## Guardrails (must comply)

- No new facts introduced
- No invented metrics
- Facts match person master
- No sensitive/confidential info

(See ADR-006.)

---

## Execution log

### Week-by-week

- **YYYY-W##:**
  - A submissions: __, responses: __, screens: __
  - B submissions: __, responses: __, screens: __
  - Notes:

---

## Result

- Outcome summary:
- What improved:
- What worsened:
- Confidence level: (Low / Medium / High)

---

## Decision

Choose one:

- **Keep B** (promote)
- **Iterate** (run another focused test)
- **Stop** (revert)

If promoted and it changes stable behavior:

- update `CANON_ARCH.md` (if needed)
- consider an ADR if the system behavior changes

---

## Notes

- Links to example roles:
- Links to exported resumes used:

