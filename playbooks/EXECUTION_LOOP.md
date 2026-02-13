# Execution Loop

This playbook defines the repeatable **career execution loop**.

Goal: produce outcomes (responses, interviews, offers) while keeping resume assets consistent, defensible, and lane-coherent.

---

## Canon rules referenced

- **Human authority:** person-level `RESUME_MASTER.md` remains the source of truth. (ADR-001)
- **Lane strategy:** general + lane variants derived from master. (ADR-002)
- **AI advisory:** AI may suggest; humans approve truth. (ADR-003)
- **Execution > tooling:** product work must support execution. (ADR-004)
- **Validation required:** export gate before sending. (ADR-006)

---

## Inputs

- Target lane (selected during role triage)
- Role description (JD) + company context
- Person’s lane resume variant (ATS-safe)
- Optional: portfolio links relevant to the lane

---

## Outputs

- Tailored resume (exported artifact)
- Optional: cover letter / outreach message
- Role scorecard (fit + risk + priority)
- Tracking entry (submission + follow-ups)

---

## Cadence

### Daily (execution)

- 1–3 role screens
- 0–2 tailored submissions
- 2–10 outreach messages (targeted)
- 15–45 min interview prep (only for active pipelines)

### Weekly (review)

- Log results + metrics
- Remove low-quality roles from the pipeline
- Refresh keyword sets and lane coherence as needed

---

## Loop steps

### Step 1 — Role intake

Collect:

- JD text (copy/paste)
- role title, location, level
- must-have requirements
- pay range (if available)
- application deadline (if known)

Record in:

- `logs/weekly/YYYY-W##.md` (summary)
- or a role tracking system (external) with a link recorded in the weekly log

---

### Step 2 — Role triage (fast gate)

Use `playbooks/ROLE_TRIAGE.md`.

Decide:

- **Apply / Outreach-first / Skip**
- Lane selection
- Priority (High/Med/Low)

If **Skip**, record the reason briefly and stop.

---

### Step 3 — Choose base resume

Select the lane variant:

- `variants/RESUME_<LANE>.md` (ATS-safe)

If the lane variant is missing, do not invent a new resume.

Instead:

- create a minimal lane variant from the master (owner-approved)
- log it as an experiment if it is a new lane structure

---

### Step 4 — Tailor (tight scope)

Tailoring is allowed to change:

- summary emphasis
- skills ordering
- bullet selection and ordering
- keyword alignment (without changing facts)

Tailoring must not:

- add new facts not present in the master
- introduce invented metrics
- include confidential employer/customer details

If new facts are needed, update the **person master** first (owner-approved).

---

### Step 5 — Validate (export gate)

Apply the minimal checklist from ADR-006:

- facts match the master (dates/titles/locations)
- no sensitive/confidential data
- no invented metrics; bullets defensible
- ATS-safe formatting
- lane identity coherent

If validation fails, fix before submitting.

---

### Step 6 — Export and submit

Export tailored artifacts to the shared workspace:

- `careers/people/<name>/resume_exports/`

Submit the application.

Record:

- date/time
- link to job posting
- role title + company
- which resume variant was used

---

### Step 7 — Outreach (preferred)

Send targeted outreach to:

- hiring manager (if identifiable)
- team members
- recruiter

Use:

- `playbooks/NETWORKING_OUTREACH.md`
- `templates/OUTREACH_EMAIL_TEMPLATES.md`

Log:

- who, when, channel, and next follow-up date

---

### Step 8 — Interview prep (only when earned)

Start deep prep when one of the following is true:

- recruiter screen scheduled
- technical screen scheduled
- strong referral path exists

Use:

- `playbooks/INTERVIEW_PREP.md`

Keep prep lane-aligned and role-specific.

---

### Step 9 — Follow-up loop

- follow up 3–7 days after submission (unless instructed otherwise)
- follow up after outreach if no response
- close loop when role is filled or rejected

Log outcomes in the weekly review.

---

## Definition of Done

A role is “done” for the week when:

- triage decision recorded
- if applied: submission recorded + resume exported + follow-up plan created
- if outreach-first: outreach logged + next step date set
- if skipped: reason recorded

---

## Logs and measurement

### Weekly review

Use:

- `scorecards/WEEKLY_REVIEW_TEMPLATE.md`

Track:

- roles screened
- applications submitted
- outreach messages sent
- responses
- interviews scheduled
- rejections
- time spent on execution vs tooling

### Decision log

System-level changes (lane definitions, validation rules, repo boundaries) require:

- an ADR and/or
- a `logs/decisions/YYYY-MM.md` entry

---

## Anti-patterns

Avoid:

- building tooling instead of executing
- creating many role-specific resumes (variant explosion)
- adding facts directly into exported resumes (bypassing master)
- publishing sensitive/confidential info
- “spray and pray” applications without lane coherence

---

## Related documents

- `playbooks/ROLE_TRIAGE.md`
- `playbooks/NETWORKING_OUTREACH.md`
- `playbooks/INTERVIEW_PREP.md`
- `playbooks/OFFER_NEGOTIATION.md`
- `scorecards/METRICS.md`
- ADR-001 … ADR-006

