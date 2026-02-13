# Metrics

This document defines the **minimum set of metrics** used to run the career execution loop.

Goal: measure progress without turning the system into bureaucracy.

---

## Principles

- Metrics exist to **change behavior**, not to create reporting.
- Prefer **leading indicators** (inputs you control) over lagging indicators (outcomes you don’t).
- Track per-person metrics separately, then optionally roll up at company level.

---

## Metric set (canonical)

### A) Execution inputs (leading)

1. **Roles screened**
   - Count of JDs triaged (Apply / Outreach-first / Skip)

2. **Applications submitted**
   - Count of completed submissions

3. **Outreach messages sent**
   - Count of targeted messages (LinkedIn/email), excluding spammy mass sends

4. **Follow-ups sent**
   - Count of follow-ups on prior submissions/outreach

---

### B) Pipeline outcomes (lagging)

5. **Responses**
   - any reply from recruiter/hiring manager/team member

6. **Screens scheduled**
   - recruiter screen or hiring manager intro scheduled

7. **Technical interviews scheduled**

8. **Offers / final rounds**

---

### C) Quality and control

9. **Lane coherence score (self-check)**
   - Pass/Fail each submission:
     - one lane identity
     - facts consistent with master
     - no invented metrics

10. **Time split**
   - estimate weekly hours:
     - execution (applications/outreach/interviews)
     - tooling/product work (Jobify-AI/docs)

---

## Suggested weekly targets (default)

These are default targets; adjust after 2–3 weeks based on response rates and bandwidth.

### Baseline (steady)

- Roles screened: **10–20**
- Applications: **3–8**
- Outreach messages: **15–40**
- Follow-ups: **5–15**
- Time split: **≥70% execution**

### Aggressive (short runway)

- Roles screened: **20–40**
- Applications: **8–15**
- Outreach messages: **40–80**
- Follow-ups: **10–25**
- Time split: **≥85% execution**

### Low bandwidth (maintenance)

- Roles screened: **5–10**
- Applications: **1–3**
- Outreach messages: **5–15**
- Follow-ups: **2–6**
- Time split: **≥60% execution**

---

## Interpreting results

### If applications are high but responses are low

Likely issues:

- lane mismatch / mixed identity
- weak keyword alignment
- weak proof/artifacts
- applying to overly competitive roles without referral

Actions:

- strengthen lane variants
- prioritize outreach-first
- run an ATS keyword delta experiment

---

### If outreach is high but replies are low

Likely issues:

- message too long or generic
- unclear ask
- weak artifact relevance

Actions:

- shorten messages
- include one concrete artifact
- narrow to fewer companies, deeper outreach

---

### If tooling time dominates

Risk:

- “building the tool” replaces execution (ADR-004)

Action:

- set a hard cap on tooling hours for the next week
- ship one minimal improvement only if it removes a recurring execution bottleneck

---

## Where metrics are recorded

- Weekly rollup: `logs/weekly/YYYY-W##.md`
- Per-role scoring: `scorecards/ROLE_SCORECARD_TEMPLATE.md`

---

## Change control

If you change the canonical metric set (add/remove items), record the decision in an ADR and update:

- `CANON_ARCH.md`
- `governance/CHANGELOG.md`

