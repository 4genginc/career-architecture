# Risk Register

This register tracks the main risks in the multi-person career system.

**Purpose:** make risks visible, define mitigations, and avoid repeating failures.

---

## How to use

- Add a new risk when it could realistically cause harm (time loss, reputation loss, privacy leak, legal risk, missed opportunities).
- Review in weekly cadence (see `scorecards/WEEKLY_REVIEW_TEMPLATE.md`).
- When a mitigation becomes stable practice, reflect it in `CANON_ARCH.md` or an ADR.

---

## Risk log

| ID | Risk | Likelihood | Impact | Mitigation | Trigger / Early warning | Owner | Status |
|---:|---|---|---|---|---|---|---|
| R-001 | Resume drift across variants (dates/titles differ) | Medium | High | Enforce master authority; export from master; validation gate | Conflicting dates across files; “which is correct?” questions | Person owner | Active |
| R-002 | Mixed identity resume (too many lanes in one doc) | Medium | High | Lane-based variants; role triage before export | Recruiter feedback: “unclear fit”; low response rate | Person owner | Active |
| R-003 | AI hallucination/exaggeration enters resume | Medium | High | AI advisory only; require human review; no invented metrics | Bullets contain numbers not backed by evidence | System owner | Active |
| R-004 | Sensitive personal data accidentally published | Low | Very High | Public/private checklist; second-person review for exports | New file includes address/DOB/SSN/immigration info | System owner | Active |
| R-005 | Confidential employer/customer info disclosed | Low | Very High | Sanitize project details; avoid naming customers; focus on role/impact | Bullets mention internal systems or undisclosed customer info | Person owner | Active |
| R-006 | Tool building replaces job search execution | High | Medium | Weekly execution minimums; separate product vs execution mode | Many commits, few submissions/outreach | System owner | Active |
| R-007 | Over-variant explosion (too many resumes) | Medium | Medium | Cap variants (<=5 active per person); archive old | Confusion about “latest” version | Person owner | Active |
| R-008 | Unreliable metrics (tracking not maintained) | Medium | Medium | Minimal weekly log template; automate capture later | Missing weekly reviews; no trend visibility | System owner | Active |
| R-009 | Collaboration causes identity mixing (bullets copied between people) | Low | High | Identity isolation rule; owner approval | Similar wording/claims appear in multiple people’s resumes | System owner | Active |
| R-010 | Public portfolio claims exceed defensible proof | Medium | High | Link artifacts; keep claims concrete; validation gate | Asked “show me” and cannot | Person owner | Active |

---

## Severity scale (guidance)

- **Likelihood:** Low / Medium / High
- **Impact:** Low / Medium / High / Very High

---

## Notes

- This register is a living document. When a risk is fully mitigated by stable policy, capture it in CANON or ADRs.
