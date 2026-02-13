# Networking & Outreach

This playbook defines a repeatable outreach process that increases response rates and creates referral paths.

Principle: **Outreach is part of execution**, not an optional add-on. (See `playbooks/EXECUTION_LOOP.md`.)

---

## Inputs

- Target company and role
- Lane selection (Backend / Embedded / AI Platform / UIUX)
- 1–2 strongest relevant artifacts (repo, demo, write-up)
- A specific ask (10–15 minute chat, referral advice, recruiter contact)

---

## Outputs

- 3–10 messages sent per target company
- Follow-up plan with dates
- Notes captured for future tailoring

---

## The outreach stack (preferred order)

1. Warm intros (best)
   - former coworkers
   - friends
   - alumni
   - customers/partners

2. Targeted internal contacts
   - hiring manager (if identifiable)
   - team members close to the role

3. Recruiters
   - internal recruiter
   - talent partner

4. Public community
   - technical communities
   - meetups
   - GitHub maintainers (if relevant)

---

## Message design rules

- Keep it short (5–8 lines).
- Make it specific to their team.
- Show one concrete relevant artifact.
- Ask one clear question.
- Make it easy to say yes.

Avoid:

- long autobiographies
- generic “I’m interested” without specificity
- attaching large files immediately
- exaggerated claims

---

## Templates (high-level)

Use the detailed templates in:

- `templates/OUTREACH_EMAIL_TEMPLATES.md`

This playbook provides the structure and sequencing.

---

## Sequence

### Day 0 (same day as apply)

- Send 2–3 messages:
  - 1 hiring manager (or closest match)
  - 1 team member
  - 1 recruiter (if known)

Log who/when.

### Day 3–5 (follow-up #1)

- Follow up on the strongest contact first.
- Keep follow-up even shorter.

### Day 10–14 (follow-up #2)

- One final follow-up if role still open.
- If no response, close the loop and move on.

---

## What to say (content blocks)

Pick 2–3 blocks per message:

1. **Context**
   - “I’m applying for <role> on <team>.”

2. **Fit signal (lane-aligned)**
   - “My background is <lane>, with recent work in <1–2 relevant areas>.”

3. **Artifact**
   - “Here’s a relevant artifact: <repo/demo/doc>.”

4. **Ask**
   - “Would you be open to a 10–15 minute chat?”
   - “Is this role aligned with your team’s current needs?”
   - “If not you, who would you suggest I speak with?”

5. **Close**
   - “Either way, thanks for your time.”

---

## Logging

Log outreach in one of:

- `logs/conversations/informational_interviews.md` (running list)
- `logs/weekly/YYYY-W##.md` (weekly rollup)

Minimum fields:

- date
- company
- person contacted
- channel (LinkedIn/email)
- outcome (no response / replied / referred / call scheduled)
- next follow-up date

---

## Quality bar

A good outreach message makes it easy for the recipient to answer in 30 seconds.

If your message needs a long explanation, it’s too long.

---

## Related docs

- `playbooks/ROLE_TRIAGE.md`
- `playbooks/EXECUTION_LOOP.md`
- `templates/OUTREACH_EMAIL_TEMPLATES.md`
- `logs/conversations/informational_interviews.md`
