# Review & Ponytail Triage (`review.md`)

Loaded when Sudeep pastes text he wrote himself and wants it checked (`"check this"`, `"review my"`, `"does this look right"`, `"before I send"`, or a draft in his own voice with no counterparty message to answer). Follows the Ironclad Outbound Lock in `SKILL.md` (never send directly).

---

## 1. Flow (`ponytail-review` + `Negative Space` + `Edit-In-Place`)

1. **Graph-First Fact Verification (`GRAPH_REPORT.md` + `fact-check.md`):**
   - Extract every factual claim in Sudeep's draft (dates, amounts, account/loan numbers, names, availability, past agreements).
   - Check `.state/shyamal-graph/GRAPH_REPORT.md` first (`<1,200 tokens`), then run targeted delta lookups (`gmail`, `gcalendar`, `gdrive`, `notion-api`, local files) only for claims not already `[EXTRACTED]` in the graph.
2. **`ponytail-review` Context & 3-Tier Triage (`references/thinking-models.md`):**
   - Read the connected context around the message (the latest reply in the thread, calendar conflicts, and `self/stance.md`).
   - Evaluate through three lenses:
     - **Counterparty Role Swap (`claude-creativity`):** How will the recipient (bank officer, recruiter, VP, vendor, family member) read this under *their* constraints and incentives?
     - **Negative Space Check (`claude-creativity`):** What crucial fact, statutory requirement (e.g., FEMA purpose code, FIRC request, TDS ref, PNR), or unstated boundary is **missing** from the draft that will cause a follow-up delay if omitted?
     - **Ponytail Simplification Check:** Is any part of the draft over-explaining, repeating numbers, or using defensive justification that should be cut?
   - Group findings strictly into **`Must Fix`** (factual/compliance errors, broken red lines, defensive tone), **`Should Fix`** (Negative Space omissions, duplication, over-engineering), and **`Nice to Have`** (minor rhythm polish). Omit any empty tier.
3. **`Edit-In-Place` + Two-Pass `ai-tells.md` Revision:**
   - Revise the text **once**, preserving Sudeep's own wording, cadence, and capital-after-comma habit wherever it works.
   - Swap in verified `[EXTRACTED]` facts, insert any critical Negative Space data points, fix grammar, and run the **Two-Pass `ai-tells.md` Engine** (zero em dashes, zero copula avoidance, zero `-ing` tails).

---

## 2. Output Format

```markdown
**Outbound Preview (Draft Only: Will Not Send)**
- **To:** <Recipient if known, else "Confirm recipient before sending">
- **Channel / Subject:** <Channel + Subject if applicable>

**Fact & Graph Check:** <one line per claim that is `Off`, `Outdated`, or `AMBIGUOUS`, with source and epistemic tag>
Checked and fine (`[EXTRACTED]`): <N claims (short list)>

**Ponytail Review & Negative Space:**
- **Must Fix:** <factual/compliance/stance issues, only if real>
- **Should Fix (Negative Space / Bloat):** <missing context that prevents back-and-forth, or duplication to cut, only if real>
- **Nice to Have:** <1 line max, only if real>

**Revised:**
```text
<one polished version keeping Sudeep's voice, grammar fixed, verified facts and Negative Space items woven in naturally>
```

<soft close>
```

- **Zero Padding Rule:** If `Must Fix`, `Should Fix`, or `Nice to Have` has nothing real, omit that bullet completely.
- **Single Revised Output:** Show **one** revised version (not A/B/C), because it is already Sudeep's draft.
- **Soft Close:** Name the single highest-impact fix and hand the choice back, e.g., `"Your draft had the right numbers, I just added Purpose Code P0021 and the FIRC request (Negative Space) so IDFC doesn't hold the wire. Want me to save this to your Gmail Drafts?"`
