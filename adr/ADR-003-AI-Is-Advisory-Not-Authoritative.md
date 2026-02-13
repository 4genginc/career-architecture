# ADR-003: AI Is Advisory, Not Authoritative

- **Status:** Accepted
- **Date:** 2026-02-13

---

## Context

AI assistance (LLMs, prompt-based tools, and Jobify-AI) can rapidly generate:

- resume bullets
- summaries and skill sections
- keyword rewrites for ATS
- cover letters and outreach messages

However, AI can also:

- hallucinate facts
- introduce subtle inconsistencies (dates, scope, titles)
- exaggerate impact beyond what is defensible
- drift the person’s career narrative over time

In a multi-person system, this risk increases because generated content can be copied and reused.

We need a hard rule that preserves human authority and defensibility.

---

## Decision

1. AI output is **advisory only**.
2. Only humans can create or modify **authoritative truth**:
   - person-level `RESUME_MASTER.md`
   - factual anchors (dates, titles, certifications)
   - canonical lane definitions
3. AI-generated text must be treated as one of:
   - **Draft suggestion** to be reviewed and edited
   - **Candidate phrasing** for a bullet already supported by human truth
   - **Formatting transform** that does not alter facts
4. AI must not introduce new facts unless the human explicitly supplies them.
5. Jobify-AI (or any automation) must preserve traceability:
   - outputs must reference the lane + master source used
   - outputs must not overwrite or auto-merge into the master

---

## Consequences

### Positive

- Reduces risk of untrue or exaggerated claims.
- Preserves consistency across variants.
- Makes interviews safer because claims remain defensible.
- Enables AI productivity while maintaining human control.

### Trade-offs

- Requires review time for AI-generated outputs.
- Limits “fully automatic” resume generation.
- Slower iteration if humans do not keep a clean master bullet bank.

---

## Alternatives considered

1. **AI as authoritative (auto-update master)**
   - Rejected due to hallucination risk and loss of defensibility.

2. **AI-authoritative only for formatting**
   - Partially acceptable, but still requires checks to avoid semantic drift.

3. **No AI usage**
   - Rejected; unnecessary loss of productivity.

---

## Implementation notes

### Required labeling

- AI-generated sections should be marked as **Draft** until accepted by a human.

### Validation gate

Before exporting a resume:

- confirm all claims exist in the master or are explicitly supplied by the human
- run the consistency checks in ADR-006 (Validation Requirement)

### Tooling guardrails (Jobify-AI)

- never write back to `RESUME_MASTER.md`
- provide a “diff-style” proposal when suggesting edits
- log key transformations (lane used, keyword set, job title)

---

## Links

- ADR-001 (resume repo as authority)
- ADR-006 (validation requirements)
- `CANON_ARCH.md`

