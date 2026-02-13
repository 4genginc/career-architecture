# Decision Log Template

Use this template in the private ops repo:

* `career-ops-private/logs/decisions/YYYY-MM.md`

A **decision log** records an operational choice that changes how work is executed (lanes, constraints, weekly loop, experiments, or what gets published).

**Rule:** If a decision becomes stable policy that affects the system, promote it to an **ADR** and link back to this entry.

---

## When to log a decision

Log a decision when it:

* changes a lane, positioning, or target role family
* changes constraints (location, schedule, compensation floor, work authorization assumptions)
* starts/stops an experiment
* creates a rule or policy you want to enforce later
* commits to publishing a new public artifact

Do **not** include sensitive personal data (DOB/SSN/address/medical/immigration details), private employer documentation, or customer-confidential information.

---

## YYYY-MM-DD — <short decision title>

**Status:** Proposed / Adopted / Reversed

**Decision type:** Operational / System (requires ADR)

**Owner:** <person or role>

**Effective date:** YYYY-MM-DD

**Review date (optional):** YYYY-MM-DD

**Reversibility:** Reversible / Hard to reverse

---

### Context

* What situation prompted this decision?
* What constraint or tradeoff matters most?

---

### Decision

* One sentence stating what was chosen.
* 1–3 bullets with concrete commitments or rules.

---

### Why

* Reason 1
* Reason 2

---

### Scope / impact

* **Affects:** systems, repos, lanes, workflows, metrics
* **Does not affect:** explicitly out of scope

---

### Evidence / inputs (sanitized)

* Metrics
* Recruiter feedback (summarized)
* JD analysis
* Interview notes (sanitized)

---

### Alternatives considered

* Option A: summary + why not
* Option B: summary + why not

---

### Risks

* Risk 1
* Risk 2

---

### Mitigations

* Mitigation 1
* Mitigation 2

---

### Linked docs

* **ADRs:** ADR-___ (if applicable)
* **Experiments:** EXP-___
* **Scorecards:** (optional) link
* **Weekly log:** `career-ops-private/logs/weekly/YYYY-W##.md`
* **Artifacts published:** (optional) link(s)

---

### Follow-ups

* [ ] Action 1
* [ ] Action 2

---

## Notes

* Keep the tone factual and audit-friendly.
* Prefer reversible decisions when uncertain; set a review date.
* If this decision changes system behavior, create/update an ADR and update `adr/ADR-INDEX.md` in the public repo.
