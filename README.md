# Career Architecture

This repository defines the **company-level career operating system** for 4G‑ENG.

It is a **public, reusable reference** for how we produce, validate, and maintain career assets (resumes, LinkedIn, outreach artifacts) **without mixing personal source‑of‑truth content**.

---

## Public vs private boundary

**Public (this repo):** principles, boundaries, playbooks, templates, scorecards, and experiments.

**Private (separate repo):** execution logs (weekly reviews, decision logs, outreach threads, informational interviews).

* Private repo: `career-ops-private/`
* Logs path: `career-ops-private/logs/`

---

## What this repo is

**Career Architecture** is:

* A **reference library** of principles, boundaries, and repeatable processes.
* A **governed documentation system** (CANON + ADRs) explaining why key decisions were made.
* A set of **playbooks, scorecards, templates, and experiments** that make outputs consistent and high quality.

---

## What this repo is NOT

This repo is **not** the authoritative home for any individual’s resume truth.

Do **not** store:

* full personal resumes as canonical truth
* sensitive personal data (DOB, SSN, addresses, immigration or medical details)
* private employer documentation
* outreach threads, interview notes, or other execution logs

Keep person‑specific resume truth in **person‑level resume repos**. Keep execution logs in the **private repo**.

---

## Relationship to other repos

Use a 3‑layer model:

1. **Person-level resume repos (truth)**

   * Example: `resume-<person>/` (one repo per person)
   * Holds `RESUME_MASTER.md` + lane variants + verified facts

2. **Shared workspace repo (assets + exports)**

   * Example: `careers/`
   * Holds shared playbooks plus per-person exported resumes and LinkedIn assets
   * May hold *sanitized* interview prep materials intended for sharing

3. **Automation/engine repo (generation + tooling)**

   * Example: `jobify-ai/`
   * Consumes person truth + lane rules and generates tailored outputs

This repo (`career-architecture/`) is the **company-level reference** that informs (1)–(3).

---

## Repository structure

```text
career-architecture/
├── README.md
├── CANON_ARCH.md
├── adr/
│   ├── README.md
│   ├── ADR-001-Resume-Repo-As-Human-Authority.md
│   ├── ADR-002-Lane-Based-Resume-Strategy.md
│   ├── ADR-003-AI-Is-Advisory-Not-Authoritative.md
│   ├── ADR-004-Product-Participation-vs-Career-Execution.md
│   ├── ADR-005-Collaboration-Boundary.md
│   ├── ADR-006-Validation-Requirement.md
│   └── ADR-INDEX.md
├── governance/
│   ├── PRINCIPLES.md
│   ├── BOUNDARIES.md
│   ├── RISK_REGISTER.md
│   └── CHANGELOG.md
├── playbooks/
│   ├── EXECUTION_LOOP.md
│   ├── ROLE_TRIAGE.md
│   ├── NETWORKING_OUTREACH.md
│   ├── INTERVIEW_PREP.md
│   └── OFFER_NEGOTIATION.md
├── scorecards/
│   ├── METRICS.md
│   ├── WEEKLY_REVIEW_TEMPLATE.md
│   └── ROLE_SCORECARD_TEMPLATE.md
├── experiments/
│   ├── README.md
│   ├── EXP-001-Resume-A-B-Tests.md
│   ├── EXP-002-Keywords-ATS-Delta.md
│   └── EXP-003-LinkedIn-Headline-Tests.md
├── templates/
│   ├── ADR_TEMPLATE.md
│   ├── DECISION_LOG_TEMPLATE.md
│   ├── ROLE_SCORECARD_TEMPLATE.md
│   └── OUTREACH_EMAIL_TEMPLATES.md
└── links/
    ├── TARGET_COMPANIES.md
    ├── ROLE_BOARDS.md
    └── PORTFOLIO_LINKS.md
```

---

## Repository map

* `CANON_ARCH.md`

  * Canonical, defended truth for the **company-level** career system.

* `adr/`

  * Architecture Decision Records explaining *why* decisions were made.

* `governance/`

  * Principles, boundaries, risks, and changelog for the system.

* `playbooks/`

  * Step-by-step execution loops (triage → outreach → interviews → offers).

* `scorecards/`

  * Metrics and templates for weekly review and role scoring.

* `experiments/`

  * Controlled tests for improving outcomes (ATS keywords, resume variants, LinkedIn changes).

* `templates/`

  * Reusable templates (ADR, decision logs, scorecards, outreach email templates).

* `links/`

  * Curated target companies, role boards, portfolio links.

---

## Quick start

### Add a new person

1. Create a **person-level resume repo** with:

   * `RESUME_MASTER.md`
   * `variants/RESUME_<LANE>.md`
   * `facts/` (optional) for dates/titles/certs validation

2. In `careers/` create:

   * `people/<name>/resume_exports/`
   * `people/<name>/linkedin/`
   * `people/<name>/interview_prep/`

3. Use `jobify-ai/` to generate tailored outputs, following:

   * `playbooks/ROLE_TRIAGE.md`
   * `scorecards/ROLE_SCORECARD_TEMPLATE.md`
   * `templates/OUTREACH_EMAIL_TEMPLATES.md`

4. Record execution outcomes in the private repo:

   * `career-ops-private/logs/weekly/YYYY-W##.md`

---

## Governance rules

* **CANON first:** if something is “true and defended,” it goes into `CANON_ARCH.md`.
* **Decisions are logged:** if it changes how the system works, record an ADR and update `adr/ADR-INDEX.md`.
* **Validation required:** lane resumes must be traceable back to a verified master source.
* **Privacy boundary:** personal truth stays in person-level repos; execution logs stay private.

---

## How to contribute

* New system decision → add an ADR + update `adr/ADR-INDEX.md`
* New workflow → add/update a playbook
* New measurement → update `scorecards/METRICS.md`
* New experiment → add `experiments/EXP-###-*.md`
* Weekly cadence → log in `career-ops-private/logs/weekly/YYYY-W##.md`

---

## Status

This repo is intended to remain stable and reusable. When in doubt:

1. Update a **template** first.
2. Run a small **experiment**.
3. Only then promote to **CANON**.
