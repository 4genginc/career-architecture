# Risk Register

This register tracks the main risks in the multi-person career system.

**Purpose:** make risks visible, define mitigations, and avoid repeating failures.

**Public-safe:** this file must not contain sensitive personal data, employer/customer confidential information, or private execution details.

---

## How to use

* Add a new risk when it could realistically cause harm (time loss, reputation loss, privacy leak, legal risk, missed opportunities).
* Review during weekly cadence (see `scorecards/WEEKLY_REVIEW_TEMPLATE.md`).
* When a mitigation becomes stable practice, reflect it in `CANON_ARCH.md` and/or log an ADR.

---

## Severity scale (guidance)

* **Likelihood:** Low / Medium / High
* **Impact:** Low / Medium / High / Very High

Notes:

* *Likelihood* = probability the risk occurs within the next 4–8 weeks.
* *Impact* = worst plausible damage if it occurs.

---

## Risk log

|    ID | Risk                                                                 | Likelihood | Impact    | Primary mitigation                                                                             | Trigger / early warning                                                               | Owner        | Status |
| ----: | -------------------------------------------------------------------- | ---------- | --------- | ---------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ------------ | ------ |
| R-001 | Resume drift across variants (dates/titles differ)                   | Medium     | High      | Enforce master authority; update master first; validation gate before export                   | Conflicting dates across files; “which is correct?” questions                         | Person owner | Active |
| R-002 | Mixed-identity resume (too many lanes in one doc)                    | Medium     | High      | Lane-based variants; role triage before export; cap active variants                            | Recruiter feedback: “unclear fit”; low response rate                                  | Person owner | Active |
| R-003 | AI hallucination/exaggeration enters resume                          | Medium     | High      | AI advisory only; human review; no invented metrics; validation gate                           | Bullets contain numbers/claims not backed by evidence                                 | System owner | Active |
| R-004 | Sensitive personal data accidentally published                       | Low        | Very High | Public/private checklist; second-person review for public exports; repo hygiene (`.gitignore`) | New file includes personal identifiers (address/DOB/SSN/etc.)                         | System owner | Active |
| R-005 | Confidential employer/customer information disclosed                 | Low        | Very High | Sanitize details; avoid naming confidential customers; focus on role/impact; validation gate   | Bullets reference internal systems, unreleased products, or undisclosed customer info | Person owner | Active |
| R-006 | Tool building replaces job-search execution                          | High       | Medium    | Weekly execution minimums; cap tooling hours; separate “execute” vs “tooling” mode             | Many commits, few submissions/outreach                                                | System owner | Active |
| R-007 | Variant explosion (too many resumes)                                 | Medium     | Medium    | Cap variants (≤5 active per person); archive old; clear naming conventions                     | Confusion about “latest” version; duplicate/resurrected files                         | Person owner | Active |
| R-008 | Unreliable tracking (metrics not maintained)                         | Medium     | Medium    | Minimal weekly template; keep counts lightweight; automate later if needed                     | Missing weekly reviews; no trend visibility                                           | System owner | Active |
| R-009 | Collaboration causes identity mixing (bullets copied between people) | Low        | High      | Identity isolation rule; explicit owner approval for cross-person reuse                        | Similar wording/claims appear across people’s resumes                                 | System owner | Active |
| R-010 | Public portfolio claims exceed defensible proof                      | Medium     | High      | Link artifacts; keep claims concrete; validation gate; avoid inflated scope                    | Asked “show me” and cannot demonstrate                                                | Person owner | Active |

---

## Notes

* This register is a living document.
* When a mitigation becomes stable policy, capture it in an ADR and update `CANON_ARCH.md`.
* If a risk is eliminated (or no longer relevant), change Status to **Closed** and briefly note why in the changelog.
