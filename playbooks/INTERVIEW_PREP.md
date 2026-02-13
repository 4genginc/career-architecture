# Interview Prep

This playbook defines a repeatable interview preparation process aligned to the lane and role.

Principles:

- Prep starts deep **only when earned** (screen scheduled or strong referral). See `playbooks/EXECUTION_LOOP.md`.
- Keep prep **lane-coherent**; avoid mixed identity.
- Prefer **defensible stories** over memorized trivia.

---

## Inputs

- Role description (JD)
- Lane selection
- Resume variant used for the application
- Company context (product, customers, constraints)
- Interview format (recruiter screen / hiring manager / technical / panel)

---

## Outputs

- 60–90s lane narrative
- 5–8 STAR stories mapped to the role
- Technical refresh plan (only what’s relevant)
- Questions for interviewer
- Risk list (gaps, weak points, sensitive areas)

---

## Step 1 — Confirm the interview type

### Recruiter screen

Focus:

- crisp narrative
- role fit + availability
- compensation range alignment
- work authorization / location constraints (as applicable)

### Hiring manager

Focus:

- impact stories
- decision-making and ownership
- how you work with others
- what you would do in the first 30–60 days

### Technical screen

Focus:

- lane-aligned fundamentals
- practical debugging
- system design within the role scope

---

## Step 2 — Build the role map (10–20 minutes)

Extract from the JD:

- top 5 responsibilities
- top 5 must-have skills
- 3 “nice-to-have” skills

Then map:

- 2 resume bullets per must-have
- 1 artifact (repo/demo/doc) per 1–2 responsibilities (if available)

---

## Step 3 — Prepare the narrative

### 10-second version

- “I’m a <lane> engineer focused on <2 strengths>. I’m applying because <role-specific reason>.”

### 30-second version

- 1–2 most relevant experiences
- 1 defensible impact claim
- 1 reason you fit this team now

### 60–90 second version

- timeline: past → recent → now
- 2–3 highlights that match the JD
- constraints you handle well (scale, latency, reliability, hardware limits)
- what you want next (aligned to the role)

---

## Step 4 — STAR story bank (5–8 stories)

Prepare stories across these categories:

- delivering under constraints
- debugging a hard issue
- improving performance/reliability
- cross-team collaboration
- disagreement / trade-off decision
- learning curve / ramp-up
- ownership and leadership

Each story:

- Situation
- Task
- Action
- Result
- What you learned / what you would do differently

**Rule:** stories must be consistent with resume claims (ADR-006).

---

## Step 5 — Technical refresh (only what matters)

Pick 3–5 topics that the interview is likely to probe.

### Backend/System lane examples

- Linux fundamentals (process, threads, memory, networking)
- databases (Postgres basics, indexes, transactions)
- API design and reliability (timeouts, retries, idempotency)
- system design at appropriate scale

### Embedded lane examples

- C/C++ fundamentals, memory, pointers, concurrency
- serial protocols (UART/SPI/I2C)
- debugging (logic analyzer mindset, logs, root cause)
- real-time constraints and safety

### UI/UX lane examples

- product thinking + UX process
- portfolio walkthrough
- design rationale and trade-offs

Keep it role-specific and time-boxed.

---

## Step 6 — Questions to ask

Bring 5–8 questions; pick 2–4 depending on time.

Categories:

- team mission and success metrics
- onboarding and first 30–60 days
- technical stack and constraints
- collaboration model
- how performance is evaluated
- what “great” looks like in this role

Avoid:

- questions answered on the job posting
- overly broad “what’s the culture like” without specifics

---

## Step 7 — Risk management

Create a small risk list:

- weak skills vs must-haves
- gaps in timeline
- sensitive topics (confidential projects)

Mitigation:

- prepare a truthful framing
- redirect to defensible outcomes
- avoid disclosure of confidential details

---

## Step 8 — Post-interview loop

Within 24 hours:

- write 5 bullets: what was asked, what went well, what to improve
- update the story bank if new patterns appear
- log outcome in `career-ops-private/logs/weekly/YYYY-W##.md`

---

## Artifacts

If you will share a portfolio artifact:

- make sure it is public-safe
- ensure claims match what the artifact shows
- have a 60-second walkthrough ready

---

## Related docs

- `playbooks/EXECUTION_LOOP.md`
- `playbooks/ROLE_TRIAGE.md`
- `scorecards/WEEKLY_REVIEW_TEMPLATE.md`
- ADR-006 (validation requirements)
