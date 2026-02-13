# Role Triage

This playbook helps you decide—fast—whether to **Apply**, **Outreach-first**, or **Skip**.

Goal: spend time only on roles that match a lane, fit constraints, and are winnable.

---

## Inputs

- Job description (JD)
- Company name, role title, level
- Location / remote policy
- Compensation range (if known)
- Must-have requirements
- Any hard constraints (work authorization, commute, shift, travel)

---

## Output

- Decision: **Apply / Outreach-first / Skip**
- Lane: Backend / Embedded / AI Platform / UIUX (or other defined lane)
- Priority: High / Medium / Low
- Notes: 2–5 bullets (why)

---

## Step 1 — Hard gates (skip immediately)

Skip if any true:

- role conflicts with non-negotiable constraints (location, schedule, safety, etc.)
- role requires credentials you do not have and cannot obtain quickly
- role is clearly outside all defined lanes (mixed identity risk)
- compensation is far below requirement (when known)
- role is a poor quality posting (spammy, unclear employer, no real team)

If you skip, record a one-line reason and stop.

---

## Step 2 — Lane match

Pick exactly one lane.

Questions:

- Which lane’s keywords dominate the JD?
- Which lane has the strongest defensible artifacts?
- Can the resume present one coherent identity for this role?

If you cannot choose a lane, default to **Skip** (avoid mixed identity resumes).

---

## Step 3 — Must-have coverage

List top 5 must-haves from the JD.

Score quickly:

- 5/5: strong match
- 3–4/5: workable
- 0–2/5: likely reject

If 0–2/5, choose **Outreach-first** only if you have a warm path; otherwise **Skip**.

---

## Step 4 — Signal strength

Assign a quick signal score (0–2 each):

- **Artifacts:** portfolio/GitHub/projects directly relevant
- **Story:** you can tell a clear 60–90 second narrative for the lane
- **Keywords:** your lane resume will match JD language without inventing facts
- **Recency:** relevant work is recent enough to be credible
- **Credibility:** title/level alignment (not obviously too junior/senior)

Total 0–10.

Interpretation:

- 8–10: Apply (High)
- 5–7: Apply (Medium) or Outreach-first
- 0–4: Skip unless warm path exists

---

## Step 5 — Winnability and strategy

Use these checks:

- **Network angle:** do you know anyone there? alumni, prior coworkers, customers
- **Timing:** role posted recently? hiring manager likely still engaged
- **Competition:** is it a “hot” role with huge applicant volume?
- **Location friction:** commute, on-site requirement, relocation

Decision guidance:

- **Outreach-first** when:
  - network path exists, OR
  - role is high competition and you need referral, OR
  - must-have coverage is borderline but story is strong

- **Apply** when:
  - you have clear lane match + defensible artifacts
  - must-have coverage is workable
  - resume can be tailored quickly without adding facts

---

## Step 6 — Record the triage result

Log in weekly file (`career-ops-private/logs/weekly/YYYY-W##.md`) as:

- Company — Role — Lane — Decision — Priority
- One-line reason
- Next step date (follow-up or outreach)

---

## Fast templates

### Apply (High)

- Lane: ____
- Must-have: 4/5 or 5/5
- Signal score: 8–10
- Next: tailor resume + submit today; outreach within 24h

### Outreach-first

- Lane: ____
- Must-have: 3/5
- Signal score: 5–7
- Next: send 3 outreach messages; apply after referral / response

### Skip

- Reason: lane mismatch OR hard constraint OR 0–2/5 must-have

---

## Anti-patterns

Avoid:

- applying without lane selection
- tailoring by inventing facts
- spending hours on low-fit roles
- using “GENERAL” resume for a clearly lane-specific role

---

## Related docs

- `playbooks/EXECUTION_LOOP.md`
- `playbooks/NETWORKING_OUTREACH.md`
- `scorecards/ROLE_SCORECARD_TEMPLATE.md`
