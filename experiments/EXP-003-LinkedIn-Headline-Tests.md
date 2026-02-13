# EXP-003 — LinkedIn Headline Tests

**Status:** Draft (ready to run)  
**Owner:** 4G-ENG Careers  
**Last updated:** 2026-02-13  
**Goal type:** Discovery signal → inbound / interview pipeline

---

## 1) Purpose
Validate which LinkedIn headline formulation produces the best **recruiter discovery** and **qualified inbound** for a chosen role lane.

This experiment is not about hype. It is about:
- using role-standard terminology (searchability)
- communicating scope and seniority clearly
- increasing relevant profile views and recruiter messages

---

## 2) Hypothesis
If the headline is written as a clear **role + proof keywords + scope signal** (rather than title-only), then:
- search appearances and profile views increase
- inbound messages are more role-aligned
- outbound connection acceptance and reply rate improve

---

## 3) Constraints and Guardrails
- **Truth constraint:** every keyword must be supported by real experience, projects, or training.
- **Single-variable rule:** change only the headline during a test window.
- Keep constant during the experiment:
  - profile photo, About, Experience, Featured links, Open-to-Work settings, posting cadence

---

## 4) Test Design
### 4.1 Why “sequential tests” (not true A/B)
LinkedIn does not support simultaneous A/B tests on a single profile. We therefore use **time-sliced variants**.

### 4.2 Test window
- Recommended: **7 days per variant** (minimum), using the same weekly activity level.
- Run **4–8 variants** per lane.

### 4.3 Lanes
Pick one lane for the experiment run (do not mix lanes in one run):
- Lane A: Linux Backend / Systems
- Lane B: Embedded / RF / Electronics
- Lane C: AI Systems / RAG / Agents (only if you want that positioning)

---

## 5) Headline Patterns (choose one pattern per variant)
### Pattern P1 — Role + Core Skills + Domain
`<Target Role> | <2–4 core skills> | <domain/context>`

### Pattern P2 — Role + Outcomes + Keywords
`<Target Role> | <outcome verb phrase> | <keywords>`

### Pattern P3 — Seniority / Scope + Role + Keywords
`<Scope signal> <Target Role> | <keywords> | <systems context>`

### Pattern P4 — Role + Differentiator + Keywords
`<Target Role> | <differentiator> | <keywords>`

Notes:
- Keep punctuation consistent (use `|` separators).
- Avoid internal jargon that recruiters won’t search.
- Ensure the first ~60–80 characters still make sense when truncated.

---

## 6) Metrics
### 6.1 Primary metrics (per 7-day window)
- **Search appearances** (LinkedIn analytics)
- **Profile views**
- **Inbound recruiter messages** (count; tag as qualified/unqualified)

### 6.2 Secondary metrics
- Connection request acceptance rate (outbound)
- Response rate to outreach messages
- “Qualified inbound ratio” = qualified inbound / total inbound

### 6.3 Qualification rubric (for inbound)
Count as **qualified** if it matches the lane and level you are targeting.
- Role family matches lane
- Location/remote is plausible
- Compensation band is plausible
- Domain constraints acceptable (no clearance-only roles if you won’t pursue them)

---

## 7) Procedure
### Step 0 — Freeze baseline
Record current headline and analytics snapshot (7 days prior if available):
- headline text
- search appearances
- profile views
- inbound count

### Step 1 — Prepare variants
Create 4–8 headline variants for the chosen lane (see templates below).

### Step 2 — Run sequential windows
For each variant:
1. Set headline
2. Keep activity constant for 7 days
3. At end of window, record metrics
4. Save qualitative notes (message quality, confusion signals)

### Step 3 — Choose winner
Pick the headline that improves **primary metrics** without reducing qualified inbound ratio.

### Step 4 — Promote result
If accepted, update:
- `resume/linkedin/headline_about.md` (source-of-truth text)
- log decision in `career-ops-private/logs/decisions/YYYY-MM.md`

---

## 8) Data Capture Templates
### 8.1 Variant log table
| Variant ID | Lane | Headline | Pattern | Dates | Search appearances | Profile views | Inbound (total) | Inbound (qualified) | Qualified ratio | Notes |
|---|---|---|---|---|---:|---:|---:|---:|---:|---|
| H-01 |  |  |  |  |  |  |  |  |  |  |

### 8.2 Activity control checklist (per window)
- [ ] Same number of connection requests sent (±10%)
- [ ] Same posting cadence (0 / 1 / 2 posts)
- [ ] Same number of comments/engagement actions
- [ ] No other profile edits

---

## 9) Headline Variant Templates
Fill these with lane-specific keywords.

### Lane A (Linux Backend / Systems)
- H-A1: `Linux Backend Engineer | C/C++ • Python | Networking • Concurrency • Observability`
- H-A2: `Backend / Systems Engineer | Linux • Performance • Reliability | C/C++ • Python`
- H-A3: `Senior Systems Engineer | Linux • Networking • Distributed Systems | C/C++ • Python`
- H-A4: `Linux Backend Engineer | API Services • Datastores • Monitoring | C/C++ • Python`

### Lane B (Embedded / RF / Electronics)
- H-B1: `Embedded / RF Engineer | C/C++ • Linux | Drivers • Protocols • Test & Debug`
- H-B2: `Electronics & Embedded Engineer | SDR • RF Systems | C/C++ • FPGA (where true)`
- H-B3: `Embedded Systems Engineer | RTOS • Device Drivers | UART/SPI/I2C • Linux`
- H-B4: `RF / Embedded Engineer | SDR Integration | C/C++ • Python • Lab Validation`

### Lane C (AI Systems / RAG / Agents)
Only use if this is your intentional positioning.
- H-C1: `AI Systems Engineer | RAG • Tooling • Evaluation | Python • APIs • Deployment`
- H-C2: `LLM Engineer | RAG Pipelines • Agents | Cost Monitoring • Production Patterns`
- H-C3: `AI Platform / Backend Engineer | Retrieval • Orchestration | Python • FastAPI`
- H-C4: `AI Engineer | RAG • Guardrails • Observability | Shipping-focused prototypes`

Replace or remove any keyword that is not fully supported.

---

## 10) Decision Rules
Adopt a winner if, compared to baseline:
- Search appearances increase by **≥ 20%**, OR
- Profile views increase by **≥ 15%**, OR
- Qualified inbound increases by **≥ 1/week**,
AND
- Qualified inbound ratio is **not worse** than baseline.

If results are noisy:
- extend the winning 2 variants for an additional 7 days each

---

## 11) Risks & Mitigations
**Risk:** Headline becomes a keyword list with weak human readability.
- Mitigation: keep a clear role phrase first; limit to 2–4 high-signal keywords.

**Risk:** Mixing lanes confuses recruiters.
- Mitigation: run one lane per experiment cycle; keep the rest of the profile consistent.

**Risk:** Seasonal variation or inconsistent activity makes results unreliable.
- Mitigation: use activity checklist; run at least 4 windows.

---

## 12) Results (fill after running)
**Lane tested:**

**Baseline headline:**

**Winner headline:**

### Summary
- Best variant ID:
- Baseline → Winner deltas:
  - Search appearances:
  - Profile views:
  - Qualified inbound:

### Decision
- [ ] Adopt winner headline
- [ ] Iterate variants and rerun
- [ ] Change lane and restart

