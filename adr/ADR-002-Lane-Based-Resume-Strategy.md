# ADR-002: Lane-Based Resume Strategy

- **Status:** Accepted
- **Date:** 2026-02-13

---

## Context

A single resume cannot efficiently optimize for all targets at once:

- different roles prioritize different skill signals
- ATS keyword match varies by lane
- recruiters reject “mixed identity” resumes

At the same time, maintaining many independent resumes causes drift:

- facts diverge (dates/titles)
- bullets mutate without traceability
- different versions conflict during interviews

We need a scalable strategy that supports targeted resumes **without fragmentation**.

---

## Decision

1. Each person maintains:
   - **one master resume**: `RESUME_MASTER.md`
   - **one general resume**: `variants/RESUME_GENERAL.md`
   - **2–4 lane resumes**: `variants/RESUME_<LANE>.md`

2. A **lane resume** is a curated slice of the master:
   - includes only relevant bullets
   - reorders content for lane coherence
   - adjusts summary/skills to match the lane
   - does **not** introduce new facts that are absent from the master

3. Lane definition is owned at the company level:
   - lane purpose and boundaries are defined in playbooks and governance
   - per-person variants implement those lane rules

4. Variant count is capped to control maintenance:
   - recommended maximum: **5 active resumes per person** (1 master + 1 general + up to 3 lanes)

---

## Consequences

### Positive

- Stronger role fit signals with less “mixed identity” risk.
- Faster tailoring: pick lane, then do minor role-specific edits.
- Lower drift risk because the master remains authoritative.
- Enables multi-person scaling with consistent structure.

### Trade-offs

- Requires discipline to keep lane resumes as filtered views.
- Some achievements may fit multiple lanes and must be duplicated intentionally.
- Needs a periodic review cycle (weekly or monthly) to keep variants aligned.

---

## Alternatives considered

1. **Only one general resume**
   - Rejected because it underperforms for targeted roles.

2. **Unlimited variants per lane / per role**
   - Rejected due to maintenance cost and drift.

3. **Separate masters per lane**
   - Rejected because it guarantees drift over time.

---

## Implementation notes

### Recommended lane set (initial)

- Linux Backend / Systems
- Embedded Systems
- AI Platform / Agentic Systems (only if supported by defensible artifacts)
- UI/UX (Design lane)

### Lane resume design rules

- One headline identity per resume.
- Skills list is lane-aligned; avoid dumping every tool.
- Bullets are impact-first; avoid vague wording.
- Keep formatting ATS-safe unless explicitly producing a designed PDF.

### Export rule

Only lane variants (and general) are exported to shared workspaces (`careers/people/.../resume_exports/`).
The master stays in the person repo.

---

## Links

- ADR-001 (resume repos as authority)
- ADR-006 (validation requirements)
- `playbooks/ROLE_TRIAGE.md`
- `scorecards/ROLE_SCORECARD_TEMPLATE.md`

