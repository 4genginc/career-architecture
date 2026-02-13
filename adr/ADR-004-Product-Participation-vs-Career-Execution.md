# ADR-004: Product Participation vs Career Execution

- **Status:** Accepted
- **Date:** 2026-02-13

---

## Context

Building Jobify-AI (and related documentation) is valuable as:

- a portfolio artifact
- a control plane for repeatable career work
- a way to systematize resume tailoring and tracking

However, there is a common failure mode:

- spending weeks “building the tool”
- while not executing the actual job search loop

This risk increases when multiple people share the system (Rongjun, Mingjun, later Weijie), because tooling work can feel productive even when it does not produce interviews.

We need a clear boundary between:

- **product participation** (building the system)
- **career execution** (using the system to create outcomes)

---

## Decision

1. We maintain two distinct work modes:

   - **Product Participation Mode**
     - building `jobify-ai/` and shared docs/templates
     - improving automation, UX, and documentation

   - **Career Execution Mode**
     - role triage
     - resume tailoring + submission
     - outreach/networking
     - interview prep
     - offer negotiation

2. The weekly cadence prioritizes **Career Execution**.

3. Product Participation is allowed only when:

   - it removes a recurring bottleneck in execution, OR
   - it creates a defensible portfolio artifact that improves credibility

4. Every Product Participation item must map to a measurable execution benefit:

   - time saved per application
   - improved ATS match rate
   - higher response rate
   - reduced drift / fewer errors

5. If a tool feature does not clearly improve execution, it is deprioritized.

---

## Consequences

### Positive

- Prevents “tool building as procrastination.”
- Ensures the system produces real outcomes (interviews, offers).
- Keeps effort aligned with the company-first strategy and runway.
- Improves multi-person coordination by prioritizing shared execution wins.

### Trade-offs

- Some tool improvements will be delayed.
- Portfolio polish may be slower.
- Requires discipline to log and measure execution outcomes.

---

## Alternatives considered

1. **Build Jobify-AI first, then job search later**
   - Rejected because it delays outcomes and increases risk.

2. **No tooling or product work at all**
   - Rejected; the tool provides leverage and portfolio value.

3. **Ad-hoc balance without rules**
   - Rejected; tends to drift toward product work.

---

## Implementation notes

### Weekly execution minimums (suggested)

- X role screens
- Y submissions
- Z outreach messages
- 1 weekly review entry

(Exact numbers are configured in `scorecards/METRICS.md` and revisited as needed.)

### Logging rule

- execution outcomes are recorded in `logs/weekly/YYYY-W##.md`
- tool work is recorded in `logs/decisions/YYYY-MM.md` (or an ADR if it changes system behavior)

---

## Links

- `playbooks/EXECUTION_LOOP.md`
- `scorecards/METRICS.md`
- ADR-003 (AI is advisory, not authoritative)
