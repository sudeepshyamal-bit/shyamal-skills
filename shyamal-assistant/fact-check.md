# Fact Check & Graphify Provenance (`fact-check.md`)

Shared by `shyamal-assistant` and `shyamal-sweep`. Sudeep's supplied data points are leads, not unverified facts. Check every factual claim against `.state/shyamal-graph/GRAPH_REPORT.md` and live personal sources before it shapes a reply, decision, or sweep dossier. **Suggest, never block:** always produce the draft or plan and hand the choice back to him.

---

## 1. Lazy-Load & Graph-First Token Rule
- **Skip When No Claims Exist:** If Sudeep's prompt is a pure tone check, greeting, or conceptual question with zero factual claims (no dates, numbers, statuses, or attributions), skip running fact-check lookups entirely to save tokens.
- **Graph-First Resolution (`<1,200 tokens`):**
  1. Check `c:\Users\sudee\OneDrive\Documents\Antigravity-Data\.state\shyamal-graph\GRAPH_REPORT.md` **first**.
  2. If the fact is already recorded as `[EXTRACTED: 1.0]` in `GRAPH_REPORT.md` (e.g., BOI loan number, disbursed balance, RSU trade price, salary/bonus split, spouse net pay), verify directly against the graph and run at most a lightweight delta check (`newer_than:7d --max-results 5`) if the status could have changed this week.
  3. Only fire broader source queries when the claim is missing from `GRAPH_REPORT.md` or marked `[AMBIGUOUS]`.

---

## 2. What Counts as a Claim & Authoritative Source Mapping
- **Dates & times** (flights, trains, interviews, due dates, calendar blocks) -> `GRAPH_REPORT.md`, `gcalendar`, `gmail` (`--max-results 10`, read matched thread to the **very last message** via `gmail threads get`).
- **Numbers & financials** (amounts, salary/bonus, RSU shares, loan balances, Pre-EMI, tax, margin) -> `GRAPH_REPORT.md`, local `.csv`/`.md` in `Antigravity-Data`, `gsheets`, `gmail`.
- **Commitments & compliance status** (booking confirmed vs. waitlisted, bill paid, Form 26QB filed, FIRC received, nominee added) -> `gmail` (latest message in thread), `gdrive`.
- **People & attributions** (interviewer titles, bank officer/RM names, who promised what) -> `GRAPH_REPORT.md`, `relationships/`, `gmail`, `search_web`.

---

## 3. Verification Labels + Graphify Epistemic Tags

Combine the verification status with Graphify's epistemic confidence tag (`[EXTRACTED]`, `[INFERRED]`, `[AMBIGUOUS]`):

- **`Verified [EXTRACTED]`**: Primary record matches Sudeep's claim verbatim (confidence `1.0`).
- **`Verified [INFERRED]`**: Holds true when synthesized across 2+ records (confidence `0.70-0.99`; state the bridge briefly).
- **`Off [EXTRACTED]`**: Authoritative source says something different. State what the source says and cite it in one clause (`Gmail from Pravalika Allu, BOI ITPL, Nov 12`).
- **`Outdated [EXTRACTED]`**: Was true earlier in the thread or tracker, but settled or updated in a later message (`settled Nov 14`).
- **`Couldn't confirm [AMBIGUOUS]`**: No matching primary record found across checked sources (`<0.70` confidence). Flag gently for Sudeep's 1-line confirmation.

---

## 4. Negative Space & Approach Check
- **Approach Check:** Test the stance against `self/stance.md` and `ponytail`'s 7-Rung Ladder (altitude, calm non-defensive framing, visible displacement cost, actionable close). At most 2 concise points.
- **Negative Space Gap Check (`claude-creativity`):** Surface up to 3 high-impact facts or compliance requirements present in the records (or conspicuously missing from the thread, like a 30-day TDS window or missing Purpose Code) that Sudeep left out.

---

## 5. Tone & Rendering
- **Gentle, zero-ego phrasing:** `"Looks like ₹94,074/mo, not ₹50,071/mo (`[EXTRACTED]` BOI ITPL email, Nov 12)"`. Never scold, never say `"you're wrong"`.
- **Compact rendering at the top of output:**
  - One line per claim that is `Off`, `Outdated`, or `Couldn't confirm [AMBIGUOUS]`.
  - Collapse all verified claims into one summary line: `Checked and fine ([EXTRACTED]): N claims (<short list>)`.
