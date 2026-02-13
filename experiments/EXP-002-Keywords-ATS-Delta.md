# EXP-002 — Keywords / ATS Delta

**Status:** Draft (ready to run)  
**Owner:** Rongjun Geng  
**Last updated:** 2026-02-13  
**Goal type:** Resume → screening signal

---

## 1) Purpose
Measure how much **keyword alignment** changes (the “ATS delta”) when applying a controlled, repeatable keyword strategy to an existing resume.

This experiment is not about “gaming ATS.” It is about:
- reducing false negatives (qualified resume rejected)
- improving clarity and matchability
- ensuring the resume uses the same vocabulary as the job description

---

## 2) Hypothesis
If we apply a consistent keyword strategy (targeted terminology, skill clustering, and role-appropriate phrasing) while keeping truthfulness and seniority intact, then:
- keyword match score vs. the job description increases
- recruiter/ATS parsing quality improves (fewer missing skills)
- callback rate improves for the same role family

---

## 3) Definitions
**ATS delta:**
- Δ(match score) between **Baseline Resume** and **Keyword-Optimized Resume** against the same job description.

**Match score (local):**
- a simple, transparent metric based on keyword coverage and weighting.

**Truth constraint:**
- keywords must be supported by real experience (project, responsibility, tool usage, or training).

---

## 4) Experiment Design
### 4.1 Inputs
- **Baseline resume**: current version (control)
- **Job descriptions (JDs)**: 10–20 JDs in one role family (e.g., Linux Backend Engineer / Systems / Embedded / AI Systems)
- **Keyword strategy rules**: defined below

### 4.2 Outputs
- Keyword-optimized resume (variant)
- Scoring sheet (baseline vs variant)
- Notes: what changed, what was rejected, what felt unnatural

### 4.3 Control vs Variant
**Control (A):** Baseline resume, no changes per JD.

**Variant (B):** One keyword strategy pass, then frozen for scoring.

Important: avoid “per-JD micro-editing” during scoring. The point is a general strategy, not one-off tailoring.

---

## 5) Keyword Strategy Rules
### 5.1 Allowed changes
- add missing but true skills/tools (where evidence exists)
- normalize terminology (e.g., “CI/CD” vs “continuous integration”) when appropriate
- add a compact **Skills / Technologies** block (if missing)
- rephrase bullets to include role-standard nouns/verbs
- group related keywords (e.g., Linux + networking + concurrency)

### 5.2 Forbidden changes
- claiming experience not actually held
- inflating titles/tenure
- adding certifications/licenses not held
- adding hard requirements you do not meet (security clearance, specific regulated domains, etc.)

### 5.3 Keyword placement priorities
1. **Headline / summary** (highest leverage)
2. **Skills block** (ATS-friendly)
3. **Most recent role bullets** (proof)
4. Older roles (only if meaningful)

---

## 6) Scoring Method
### 6.1 Build the keyword set from each JD
For each JD, extract:
- **Hard skills/tools** (Linux, C/C++, Python, Docker, Kubernetes, AWS, Postgres, etc.)
- **Concepts** (concurrency, networking, performance, observability, RAG, security)
- **Role behaviors** (design reviews, incident response, ownership, mentoring)

Classify each term into one of:
- **MUST** (core requirement)
- **SHOULD** (strong preference)
- **NICE** (bonus)

### 6.2 Match scoring (simple, auditable)
For each JD:
- MUST match rate = matched_MUST / total_MUST
- SHOULD match rate = matched_SHOULD / total_SHOULD
- NICE match rate = matched_NICE / total_NICE

Compute:
- **Total Match Score** = 0.60*MUST + 0.30*SHOULD + 0.10*NICE

ATS delta:
- **Δ Score** = Score(Variant B) − Score(Control A)

### 6.3 Quality checks (non-numeric)
For each JD, record:
- **Readability impact:** improved / neutral / worse
- **Truth risk:** none / minor / unacceptable
- **Senior signal:** improved / neutral / worse

---

## 7) Procedure
### Step 1 — Collect a JD set
- Choose 10–20 job posts in a single role family.
- Save each JD as a file under:
  - `career-architecture/data/jds/ROLE_FAMILY/YYYY-MM/` (or your existing convention)

### Step 2 — Freeze the baseline
- Save baseline resume used in this experiment:
  - `career-architecture/artifacts/resume/baseline/RESUME_BASELINE_<date>.pdf`
  - `career-architecture/artifacts/resume/baseline/RESUME_BASELINE_<date>.md`

### Step 3 — Build a keyword dictionary
- For each JD, extract keywords and classify MUST/SHOULD/NICE.
- Store as:
  - `career-architecture/experiments/exp-002/keywords/JD_<id>_keywords.json`

### Step 4 — Create Variant B once
- Apply the keyword strategy to produce one optimized resume.
- Freeze it:
  - `career-architecture/artifacts/resume/variant/RESUME_KEYWORDS_V1_<date>.md`

### Step 5 — Score A vs B across all JDs
- For each JD:
  - score baseline
  - score variant
  - compute delta
  - record qualitative notes

### Step 6 — Summarize
- Compute:
  - average Δ score
  - distribution (min / median / max)
  - top keywords that caused improvement
  - keywords rejected due to truth constraint

---

## 8) Data Capture Templates
### 8.1 Per-JD scoring table (copy/paste)
| JD ID | Role | MUST A | MUST B | SHOULD A | SHOULD B | NICE A | NICE B | Score A | Score B | Δ Score | Readability | Truth risk | Senior signal | Notes |
|---|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---|---|---|---|
| JD-001 |  |  |  |  |  |  |  |  |  |  |  |  |  |  |

### 8.2 Keyword extraction checklist
- [ ] Tools / platforms
- [ ] Languages
- [ ] OS / systems
- [ ] Databases
- [ ] Cloud
- [ ] Networking
- [ ] Observability
- [ ] Security
- [ ] Architecture / design
- [ ] Collaboration / ownership

---

## 9) Decision Rules
At the end of the run:
- If **average Δ Score ≥ +0.15** with **no unacceptable truth risk**, adopt Variant B as the new “default resume.”
- If readability is worse on ≥ 30% of JDs, revise strategy to reduce keyword density and restore narrative flow.
- If senior signal decreases, revisit summary/bullets to restore ownership language and impact metrics.

---

## 10) Risks & Mitigations
**Risk:** Keyword stuffing makes the resume noisy.
- Mitigation: prioritize precision keywords; remove duplicates; keep sentences natural.

**Risk:** Terms are added without proof.
- Mitigation: every added keyword must map to an explicit bullet or a supported skills line.

**Risk:** ATS match improves but human impression worsens.
- Mitigation: track readability and senior signal; require “neutral or improved” as a gate.

---

## 11) Results (fill after running)
**JD set:** (link folder)

**Baseline resume:** (link)

**Variant resume:** (link)

### Summary
- Avg Δ Score:
- Median Δ Score:
- Min / Max Δ Score:
- % JDs improved:

### Observations
- Most common missing MUST keywords:
- Best improvements came from:
- Keywords rejected due to truth constraint:

### Decision
- [ ] Adopt Variant B
- [ ] Iterate strategy and rerun
- [ ] Abandon (reason)

---

## 12) Next Experiment Links
- EXP-003 (candidate): Section order / layout delta
- EXP-004 (candidate): Impact-metric enrichment delta

