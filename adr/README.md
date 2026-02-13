# ADRs (Architecture Decision Records)

This folder contains **Architecture Decision Records** for the career operating system.

ADRs exist to answer: **“Why did we decide this?”**

They reduce confusion, prevent drift, and make multi-person resume work scalable.

---

## When to write an ADR

Write an ADR when you:

- change lane definitions (Backend vs Embedded vs AI Platform)
- change validation requirements (facts, claims, ATS rules)
- change repo boundaries (what lives where)
- change automation behavior that affects outputs
- introduce a new execution loop or metric that changes how work is evaluated

If it’s just a draft idea or a test, use `experiments/` instead.

---

## ADR format (required sections)

Each ADR must include:

- **Title** (short, decision-like)
- **Status** (Proposed / Accepted / Deprecated / Superseded)
- **Context** (what problem prompted this?)
- **Decision** (what we decided)
- **Consequences** (trade-offs, what changes)
- **Alternatives considered** (brief)
- **Links** (to related docs, experiments, or PRs)

Use `templates/ADR_TEMPLATE.md`.

---

## Naming convention

Preferred:

- `ADR-###-Short-Title.md`

Example:

- `ADR-006-Validation-Requirement.md`

---

## Status lifecycle

- **Proposed**
  - drafted, not yet in force

- **Accepted**
  - applies immediately; update `CANON_ARCH.md` (if needed)

- **Deprecated**
  - still referenced but no longer recommended

- **Superseded**
  - replaced by a newer ADR (link both ways)

---

## Acceptance rules

An ADR may be marked **Accepted** when:

1. It has been applied at least once in real execution, OR
2. It is required for governance/safety before execution (rare), AND
3. Any impacted playbooks/templates are updated, AND
4. It is listed in `adr/ADR-INDEX.md`.

---

## Index discipline

All ADRs must be listed in `ADR-INDEX.md`:

- sorted by ADR number
- includes: title, status, date, and a one-line purpose

---

## How to modify a decision

Do not edit old ADRs to rewrite history.

Instead:

- create a new ADR
- mark the old ADR as **Superseded**
- add a link from old → new and new → old

---

## Content boundaries

ADRs must not contain:

- sensitive personal information
- private employer confidential details
- anything that should not be publishable

Store sensitive notes elsewhere (person-level repos or private storage).

