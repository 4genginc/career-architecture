# ADR Template

Use ADRs to record **system-level decisions** that change how the career operating system works.

**Public vs private rule**

* **Public ADRs** live in this repo: `adr/ADR-###-<slug>.md` and must be safe to publish.
* **Private ADRs** (containing names, compensation, specific targets, private constraints, or sensitive context) must live in the private ops repo (recommended: `career-ops-private/adr/`). Do not commit private ADRs here.

---

## Header

**ADR ID:** ADR-###
**Title:** <short decision title>
**Status:** Proposed | Accepted | Superseded | Rejected
**Date:** YYYY-MM-DD
**Owner:** <person or role>
**Decision type:** Principle | Process | Tooling | Lane | Policy
**Visibility:** Public | Private

**Supersedes (optional):** ADR-###
**Related:** ADR-###, EXP-###

---

## 1) Context

What problem are we solving?

* Current situation:
* Trigger / event:
* Constraints (truth, ethics, time, budget):
* Non-goals:

---

## 2) Decision

What we decided.

* Decision statement (1–2 sentences):
* Scope (included / excluded):
* Effective date:

---

## 3) Rationale

Why this decision is correct **for this system**.

* Reason 1:
* Reason 2:
* Supporting evidence (sanitized links, metrics summaries, experiment IDs):

---

## 4) Options considered

List the main alternatives and why they were not chosen.

### Option A — <name>

* Pros:
* Cons:
* Why not chosen:

### Option B — <name>

* Pros:
* Cons:
* Why not chosen:

---

## 5) Consequences

What changes because of this decision.

* Expected benefits:
* Costs / tradeoffs:
* New risks introduced:
* Operational impact (maintenance burden, coordination):

---

## 6) Validation

How we will know this decision worked.

* Success metrics:
* Failure signals:
* Review date:

---

## 7) Implementation notes

What must be updated to make this decision real.

* Files to change:
* Checklists / gates impacted:
* Owners:

---

## 8) Links

Cross-references for traceability.

* Related ADRs:
* Related experiments (EXP-###):
* Weekly evidence (private): `career-ops-private/logs/weekly/YYYY-W##.md` (optional)
* Decision log (private, if used): `career-ops-private/logs/decisions/YYYY-MM.md` (optional)

---

## 9) Changelog

* YYYY-MM-DD: Created
* YYYY-MM-DD: Updated (<what changed>)
