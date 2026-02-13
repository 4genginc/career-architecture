# ADR-001: Resume Repo As Human Authority

- **Status:** Accepted
- **Date:** 2026-02-13

---

## Context

In a multi-person career system, resume content can drift when it is copied across:

- multiple resume variants
- shared “careers” workspaces
- AI-assisted generation tools (e.g., Jobify-AI)

Drift creates:

- inconsistent dates/titles/locations
- conflicting claims across versions
- loss of defensibility (“where did this bullet come from?”)

We need a clear authority model for **what is true** versus what is generated or exported.

---

## Decision

1. **Each person has a dedicated “resume truth” repository** (recommended naming: `resume-<name>/`).
2. Inside each person repo, **`RESUME_MASTER.md` is the primary source of truth** for:
   - experience timeline
   - role titles and dates
   - bullet bank (claim inventory)
   - core skills summary
3. Lane resumes (variants) are treated as **filtered views** of the master, not independent truth.
4. Shared repos and tooling repos **must not become the authority**:
   - `careers/` is a workspace for shared playbooks and exported outputs.
   - `jobify-ai/` is an engine that produces suggestions and outputs.
5. Any automation output must be **traceable** back to a person’s master resume (directly or via lane variant derived from it).

---

## Consequences

### Positive

- Prevents resume drift across variants and repos.
- Makes validation feasible (facts can be checked once at the master).
- Enables multi-person scaling without identity mixing.
- Allows Jobify-AI to generate outputs without redefining truth.

### Trade-offs

- Requires discipline: edits must be applied to the master first.
- Requires export/update steps when the master changes.
- Adds mild repo overhead (one repo per person).

---

## Alternatives considered

1. **Single shared resume repo for all people**
   - Rejected due to risk of mixing identities and higher drift risk.

2. **Store all resumes in `careers/` only**
   - Rejected because `careers/` is intended to be a shared workspace and may include generated artifacts.

3. **Let Jobify-AI outputs become authoritative**
   - Rejected; violates defensibility and creates uncontrolled drift.

---

## Implementation notes

### Person-level repo minimum structure

- `RESUME_MASTER.md`
- `variants/`
  - `RESUME_GENERAL.md`
  - `RESUME_<LANE>.md` (2–4 lanes)
- Optional: `facts/` for validation anchors (dates, titles, certifications)

### Shared workspace (`careers/`)

- `people/<name>/resume_exports/` stores exported/published artifacts.

### Tooling (`jobify-ai/`)

- Inputs must include the master or lane variant.
- Outputs must never overwrite the master.

---

## Links

- `CANON_ARCH.md` (authority model and boundaries)
- ADR-002 (lane-based resume strategy)
- ADR-003 (AI is advisory, not authoritative)
