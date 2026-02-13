# ADR Index

This index lists all Architecture Decision Records (ADRs) for `career-architecture/`.

**Rule:** every ADR must be listed here.

---

## Active ADRs

| ADR | Title | Status | Date | Purpose |
|---:|---|---|---|---|
| ADR-001 | Resume Repo As Human Authority | Accepted | 2026-02-13 | Establishes that person-level resume repos are the source of truth and prevents drift. |
| ADR-002 | Lane-Based Resume Strategy | Accepted | 2026-02-13 | Defines lane variants as filtered views of a master resume to enable targeting without fragmentation. |
| ADR-003 | AI Is Advisory, Not Authoritative | Accepted | 2026-02-13 | Prevents automation from redefining human truth; AI may suggest, not assert. |
| ADR-004 | Product Participation vs Career Execution | Accepted | 2026-02-13 | Separates building Jobify-AI as an artifact from the weekly execution loop of job search. |
| ADR-005 | Collaboration Boundary | Accepted | 2026-02-13 | Defines what can be shared publicly vs kept private across family/company members. |
| ADR-006 | Validation Requirement | Accepted | 2026-02-13 | Requires defensibility, consistency, and ATS sanity checks before export. |

---

## Deprecated / Superseded

| ADR | Title | Status | Date | Notes |
|---:|---|---|---|---|
| (none) |  |  |  |  |

---

## How to add a new ADR

1. Create the file: `adr/ADR-###-Short-Title.md`
2. Use: `templates/ADR_TEMPLATE.md`
3. Add a row to **Active ADRs** above
4. If it replaces an older ADR, mark the old one as **Superseded** and link both ways

---

## Conventions

- ADR numbering is monotonic; do not renumber.
- Keep titles short and decision-like.
- Status must be one of: **Proposed**, **Accepted**, **Deprecated**, **Superseded**.
