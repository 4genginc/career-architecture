# CANON_ARCH

`CANON_ARCH.md` is the authoritative control surface for **company-level career operations**.

If a rule, boundary, workflow, or measurement is not described here (or referenced by an ADR listed here), it is **not canonical**.

This repository is intended to be **public-safe**. Execution logs and personal source-of-truth content are kept in separate repositories.

---

## Purpose

Define the **stable, defended truth** for how 4G‑ENG manages career assets across multiple people:

* resume truth ownership and anti-drift rules
* lane strategy and how variants are produced
* validation requirements (facts, claims, consistency)
* public vs private boundary
* execution loop and measurement model
* decision logging discipline (ADR)

---

## Canon scope

### Canonical

1. **Governance**

* principles, boundaries, and risk posture

2. **Process**

* role triage, outreach, interview prep, offer negotiation

3. **Quality gates**

* validation requirements for claims, structure, and formatting

4. **Artifact contracts**

* inputs/outputs expected between repos

5. **Metrics**

* weekly measurement model

### Non-canonical

* draft notes, brainstorming, raw job descriptions
* execution logs (weekly reviews, outreach threads, informational interviews)
* personal diary entries or sensitive personal data
* untested templates or speculative strategies (belongs in `experiments/`)

---

## System model

### Layer 1 — Person truth (source of authority)

**Goal:** prevent drift and mixed identity.

Each person has a dedicated resume repo (recommended naming):

* `resume-<person>/`

**Rules:**

* Each person maintains one **`RESUME_MASTER.md`** as the authoritative bullet bank.
* Lane variants are **filtered views** of the master.
* Dates, titles, employers, and locations must be consistent across all variants.
* Truth changes must be applied to the master first, then regenerated into variants.

### Layer 2 — Shared workspace (exports + shared guidance)

**Goal:** store non-sensitive exports and shared guidance.

* `careers/` contains:

  * shared docs (ATS guidance, LinkedIn templates, interview prep)
  * per-person export folders (non-sensitive outputs)

**Rules:**

* Anything intended for public sharing must be sanitized.
* Personal identifiers and private employer information must not be stored here.

### Layer 3 — Automation engine (generation tooling)

**Goal:** produce tailored outputs without becoming the authority.

* `jobify-ai/` consumes:

  * person truth (`RESUME_MASTER.md` + lane variants)
  * lane rules and templates
  * role-specific job descriptions

* It may output:

  * tailored resume drafts
  * cover letter drafts
  * role scorecards

**Rules:**

* The engine must not silently overwrite or redefine human truth.
* Outputs are drafts until accepted by a human.
* Tracking, outreach threads, and execution notes must be written to the **private repo**.

---

## Lanes and variants

A **lane** is a bounded professional identity optimized for hiring signals.

**Canonical lane set (initial):**

* Linux Backend / Systems
* Embedded Systems
* AI Platform / Agentic Systems (only if supported by defensible artifacts)
* UI/UX

**Variant policy:**

* Each person may maintain **1 GENERAL + 2–4 lane resumes**.
* More than **5 active variants** is discouraged due to maintenance cost and drift risk.

---

## Validation requirements

All resume claims must be:

1. **Defensible** (explainable; evidence available when appropriate)
2. **Consistent** (no conflicting dates/titles/locations)
3. **Concrete** (scope, constraints, outcomes; avoid vague phrasing)
4. **Non-sensitive** (no confidential employer or personal details)

**Minimum checks before export:**

* spelling/grammar pass
* ATS sanity pass (headers, dates, keyword hygiene)
* lane coherence check (no mixed identity)
* timeline consistency check

If a validation rule changes, log an ADR.

---

## Public vs private boundary

### Public-safe content

* role positioning
* sanitized achievements
* portfolio links and demos
* templates and generic playbooks
* scoring frameworks and experiments (without personal data)

### Private content (do not publish)

* personal identifiers and addresses
* immigration/medical/financial details
* employer confidential information
* internal-only performance or dispute records
* outreach logs, interview notes, informational interviews

**Private execution logs live in:**

* `career-ops-private/logs/`

---

## Canon promotion rules

An item becomes canonical only when:

1. used at least once in real execution,
2. outcome reviewed,
3. rule/template updated based on results,
4. change recorded in an ADR (when it affects system behavior).

Otherwise, keep it in `experiments/`.

---

## Decision logging discipline

Major changes require an ADR:

* lane definitions
* validation rules
* repo boundary changes
* automation behavior that affects outputs

ADRs are indexed in `adr/ADR-INDEX.md`.

---

## Canonical documents

### Core

* `README.md`
* `CANON_ARCH.md`

### Governance

* `governance/PRINCIPLES.md`
* `governance/BOUNDARIES.md`
* `governance/RISK_REGISTER.md`
* `governance/CHANGELOG.md`

### ADRs

* `adr/README.md`
* `adr/ADR-INDEX.md`
* `adr/ADR-001-Resume-Repo-As-Human-Authority.md`
* `adr/ADR-002-Lane-Based-Resume-Strategy.md`
* `adr/ADR-003-AI-Is-Advisory-Not-Authoritative.md`
* `adr/ADR-004-Product-Participation-vs-Career-Execution.md`
* `adr/ADR-005-Collaboration-Boundary.md`
* `adr/ADR-006-Validation-Requirement.md`

### Execution

* `playbooks/EXECUTION_LOOP.md`
* `playbooks/ROLE_TRIAGE.md`
* `playbooks/NETWORKING_OUTREACH.md`
* `playbooks/INTERVIEW_PREP.md`
* `playbooks/OFFER_NEGOTIATION.md`

### Measurement

* `scorecards/METRICS.md`
* `scorecards/WEEKLY_REVIEW_TEMPLATE.md`
* `scorecards/ROLE_SCORECARD_TEMPLATE.md`

### Templates

* `templates/ADR_TEMPLATE.md`
* `templates/DECISION_LOG_TEMPLATE.md`
* `templates/ROLE_SCORECARD_TEMPLATE.md`
* `templates/OUTREACH_EMAIL_TEMPLATES.md`

---

## Versioning and change control

* This file may evolve.
* Significant revisions must:

  1. update `governance/CHANGELOG.md`, and
  2. add an ADR if system behavior changes.

A repo tag may be created for major canon snapshots (example: `career-arch-v1.0`).
