# CANON_ARCH

`CANON_ARCH.md` is the authoritative control surface for **company-level career operations**.

If a rule, boundary, workflow, or measurement is not described here (or referenced by an ADR listed here), it is **not canonical**.

---

## Purpose

Define the **stable, defended truth** for how 4G ENG manages career assets across multiple people:

- resume truth ownership and anti-drift rules
- lane strategy and how variants are produced
- validation requirements (facts, claims, consistency)
- what is public vs private
- execution loop and measurement
- decision logging (ADR discipline)

---

## Canon scope

Canonical items include:

1. **Governance**
   - principles, boundaries, and risk posture
2. **Process**
   - role triage, outreach, interview prep, offer negotiation
3. **Quality gates**
   - validation requirements for claims and formatting
4. **Artifacts contracts**
   - what inputs/output formats are expected between repos
5. **Metrics**
   - how progress is measured weekly

Non-canonical items include:

- draft notes, brainstorming, raw job descriptions
- personal diary entries or sensitive personal data
- untested templates or speculative strategies (these belong in `experiments/`)

---

## System model (3 layers)

### Layer 1 — Person truth (source of authority)
**Goal:** prevent resume drift and mixed identity.

- Each person has a dedicated repo (recommended):
  - `resume-rongjun/`
  - `resume-mingjun/`
  - `resume-weijie/` (when added)

**Rules:**
- Each person maintains one **`RESUME_MASTER.md`** as the bullet bank.
- Lane variants are **filtered views** of the master.
- Dates, titles, employers, locations must be consistent across all variants.

### Layer 2 — Shared workspace (exports + shared playbooks)
**Goal:** provide a shared place to store outputs and shared guidance.

- `careers/` contains:
  - shared docs (ATS rules, LinkedIn templates, interview prep)
  - per-person export folders (non-sensitive)

### Layer 3 — Automation engine (generation tooling)
**Goal:** produce tailored outputs without becoming the authority.

- `jobify-ai/` consumes:
  - person truth (master + variants)
  - lane rules and templates
  - role-specific job description inputs
- It outputs:
  - tailored resumes
  - cover letters
  - role scorecards
  - tracking entries

**Rule:** the engine must not silently overwrite or redefine human truth.

---

## Lanes and variants

A **lane** is a bounded professional identity optimized for hiring signals.

**Canonical lane set (initial):**
- Linux Backend / Systems
- Embedded Systems
- AI Platform / Agentic Systems (only if supported by defensible artifacts)
- UI/UX (Weijie)

**Variant policy:**
- Each person may maintain **1 GENERAL + 2–4 lane resumes**.
- More than 5 active variants is discouraged due to maintenance cost.

---

## Validation requirements

All resume claims must be:

1. **Defensible** (you can explain and, when appropriate, show evidence)
2. **Consistent** (no conflicting dates/titles/locations)
3. **Concrete** (impact, scope, constraints; avoid vague “helped with”)
4. **Non-sensitive** (do not include private/confidential details)

Minimum required checks before export:
- spelling/grammar pass
- ATS sanity pass (headers, dates, keywords)
- lane coherence check (no mixed identity)
- timeline consistency check

If a validation rule changes, log an ADR.

---

## Public vs private boundary

**Public-safe content:**
- high-level role positioning
- sanitized achievements
- portfolio links and demos
- templates and generic playbooks

**Private content (do not publish):**
- personal identifiers and addresses
- immigration/medical/financial details
- employer confidential information
- internal-only performance or dispute records

---

## Canon promotion rules

Items become canonical only when:

1. they are used at least once in real execution,
2. the outcome is reviewed,
3. the rule/template is updated based on results,
4. the change is recorded in an ADR (if it affects system behavior).

Otherwise, keep them in `experiments/`.

---

## Decision logging discipline

- Major changes require an ADR:
  - lane definitions
  - validation rules
  - repo boundary changes
  - automation behavior that affects outputs

- ADRs are indexed in `adr/ADR-INDEX.md`.

---

## Canonical documents

### Core
- `README.md`
- `CANON_ARCH.md`

### Governance
- `governance/PRINCIPLES.md`
- `governance/BOUNDARIES.md`
- `governance/RISK_REGISTER.md`
- `governance/CHANGELOG.md`

### ADRs
- `adr/README.md`
- `adr/ADR-INDEX.md`
- `adr/ADR-001-Resume-Repo-As-Human-Authority.md`
- `adr/ADR-002-Lane-Based-Resume-Strategy.md`
- `adr/ADR-003-AI-Is-Advisory-Not-Authoritative.md`
- `adr/ADR-004-Product-Participation-vs-Career-Execution.md`
- `adr/ADR-005-Collaboration-Boundary.md`
- `adr/ADR-006-Validation-Requirement.md`

### Execution
- `playbooks/EXECUTION_LOOP.md`
- `playbooks/ROLE_TRIAGE.md`
- `playbooks/NETWORKING_OUTREACH.md`
- `playbooks/INTERVIEW_PREP.md`
- `playbooks/OFFER_NEGOTIATION.md`

### Measurement
- `scorecards/METRICS.md`
- `scorecards/WEEKLY_REVIEW_TEMPLATE.md`
- `scorecards/ROLE_SCORECARD_TEMPLATE.md`

### Templates
- `templates/ADR_TEMPLATE.md`
- `templates/DECISION_LOG_TEMPLATE.md`
- `templates/ROLE_SCORECARD_TEMPLATE.md`
- `templates/OUTREACH_EMAIL_TEMPLATES.md`

---

## Versioning and change control

- This file may evolve.
- Significant revisions must:
  1) update `governance/CHANGELOG.md`, and
  2) add an ADR if behavior changes.

A repo tag may be created for major canon snapshots (example: `career-arch-v1.0`).

