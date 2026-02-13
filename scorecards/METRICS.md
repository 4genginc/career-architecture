# Metrics

This document defines the **minimum set of metrics** used to run the career execution loop.

**Goal:** measure progress and improve outcomes without turning the system into bureaucracy.

---

## Principles

* Metrics exist to **change behavior**, not to create reporting.
* Prefer **leading indicators** (inputs you control) over lagging indicators (outcomes you don’t).
* Track per-person metrics separately; optionally roll up at company level.
* Keep logs **private**. Only templates and definitions live in this public repo.

---

## Data hygiene (counting rules)

To keep numbers comparable week to week:

* **Roles screened** counts **unique JDs triaged** (Apply / Outreach-first / Skip). Do not double-count the same role.
* **Applications** counts completed submissions (one role = one application).
* **Outreach** counts targeted, role-relevant messages (LinkedIn/email). Exclude mass blasts.
* **Follow-ups** counts deliberate follow-ups tied to a prior application or outreach thread.
* When a week spans holidays or time off, record the constraint in the weekly review.

---

## Canonical metric set

### A) Execution inputs (leading)

1. **Roles screened**

* Count of JDs triaged (Apply / Outreach-first / Skip)

2. **Applications submitted**

* Count of completed submissions

3. **Outreach messages sent**

* Count of targeted messages (LinkedIn/email), excluding mass sends

4. **Follow-ups sent**

* Count of follow-ups on prior submissions/outreach

---

### B) Pipeline outcomes (lagging)

5. **Responses**

* Any reply from recruiter/hiring manager/team member (including “not a fit”)

6. **Screens scheduled**

* Recruiter screen or hiring manager intro scheduled

7. **Technical interviews scheduled**

8. **Final rounds / offers**

---

### C) Quality and control

9. **Lane coherence (per submission check)**

* Mark each submission **Pass / Mixed / Needs fix** using:

  * one lane identity
  * facts consistent with master
  * no invented metrics

10. **Time split (weekly hours)**

* Estimate weekly hours:

  * execution (applications/outreach/interviews)
  * tooling/product work (Jobify-AI/docs)
  * admin/ops (optional)

---

## Optional derived metrics (for interpretation)

These are helpful, but **not required** as canonical fields:

* **Application response rate:** responses / applications
* **Screen rate:** screens scheduled / applications
* **Outreach reply rate:** replies / outreach messages
* **Follow-up yield:** responses from follow-ups / follow-ups

Use these only when you have enough volume to avoid noise (typically ≥ 10 applications or ≥ 30 outreach in the week).

---

## Suggested weekly targets (default)

Adjust after 2–3 weeks based on response rates and available bandwidth.

### Baseline (steady)

* Roles screened: **10–20**
* Applications: **3–8**
* Outreach messages: **15–40**
* Follow-ups: **5–15**
* Time split: **≥70% execution**

### Aggressive (short runway)

* Roles screened: **20–40**
* Applications: **8–15**
* Outreach messages: **40–80**
* Follow-ups: **10–25**
* Time split: **≥85% execution**

### Low bandwidth (maintenance)

* Roles screened: **5–10**
* Applications: **1–3**
* Outreach messages: **5–15**
* Follow-ups: **2–6**
* Time split: **≥60% execution**

---

## Interpreting results (common patterns)

### If applications are high but responses are low

Likely issues:

* lane mismatch / mixed identity
* weak keyword alignment
* weak proof/artifacts
* overly competitive roles without a referral path

Actions:

* strengthen lane variants (tighten identity)
* prioritize outreach-first for Tier 1 targets
* run an ATS keyword delta experiment (EXP-002)

---

### If outreach is high but replies are low

Likely issues:

* message too long or generic
* unclear ask
* weak artifact relevance

Actions:

* shorten messages; include one concrete artifact
* narrow to fewer companies; go deeper
* test 1 outreach variant at a time (track in weekly log)

---

### If tooling time dominates

Risk:

* “building the tool” replaces execution (ADR-004)

Actions:

* set a hard cap on tooling hours for the next week
* ship **one** improvement only if it removes a recurring execution bottleneck

---

## Where metrics are recorded

* Weekly rollup (private): `career-ops-private/logs/weekly/YYYY-W##.md`
* Per-role scoring: complete scorecards in the private repo (or an external tracker); keep only the **template** in this public repo.

---

## Change control

If you change the canonical metric set (add/remove items), record the decision in an ADR and update:

* `CANON_ARCH.md`
* `governance/CHANGELOG.md`
