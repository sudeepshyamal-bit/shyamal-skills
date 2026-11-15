# Playbook 3: Interview & Organisation Intelligence Dossier (`interview-sweep.md`)

Loaded when Sudeep invokes `/shyamal-sweep interview <company/role>` or asks to research an organization, prepare for an upcoming interview loop, or compile a company/interviewer prep dossier.

> [!CAUTION]
> **STRICT NO-SEND RULE**
> Never send any email, calendar response, or LinkedIn note to a recruiter or interviewer directly. Show all proposed replies (`To`, `Cc`, `Channel`, `Subject`, `Body`) in the dossier and chat preview first.

---

## 1. Wave 0 & Wave 1: Graph-First Baseline & Parallel Discovery
1. **Wave 0 (`GRAPH_REPORT.md` + Existing Career Assets):**
   - Read `.state/shyamal-graph/GRAPH_REPORT.md`, check `C:\Users\sudee\.gemini\config\skills\shyamal-assistant\relationships\recruiters-career\`, and check `Sweep-Docs/Interviews/` for any existing `.md` dossier on `<Company Name>`.
   - If refreshing an existing loop, scope Gmail queries to `after:<last_swept - 2d>`.
2. **Wave 1 Parallel Queries:**
   - **Gmail (`gmail`, `--max-results 25`):** `query: "(<Company Name> OR interview OR recruiter OR hiring OR JD OR role OR loop OR panel OR availability OR compensation OR offer) newer_than:180d"`
   - **Google Calendar (`gcalendar`):** Pull events (`-14d` to `+30d`) matching `<Company Name>`, `Interview`, `Sync`, or recruiter/interviewer emails to extract exact slot times, timezones, video links, and panelist names.
   - **Google Drive & Notion (`gdrive`, `gdocs`, `notion-api`):** Search Sudeep's career assets (`resume`, `CV`, `portfolio`, `case study`, `leadership`, `<Company Name>`, `STAR`).
   - **Web Search (`search_web`):**
     - `<Company Name>` business model, recent product/AI launches, earnings/funding momentum, and strategic pressures (last 12 months).
     - Product / UX / Design org maturity, leadership structure, and engineering partnership culture at `<Company Name>`.
     - Background, career trajectory, public talks/posts, and core KPIs of each named interviewer on the panel.

---

## 2. Wave 2: Deep Synthesis + Lateral & Creative Positioning (`thinking-models.md`)
- Read every recruiter/interview thread in Gmail to the **last message** (`gmail threads get`) and tag facts with `[EXTRACTED]`, `[INFERRED]`, or `[AMBIGUOUS]`.
- Apply four high-leverage frameworks from `shyamal-assistant/references/thinking-models.md`:
  1. **Negative Space JD & Org Read (`claude-creativity`):** Read between the lines of the job description and recruiter notes: what is the **unspoken organizational pain** (e.g., fragmented design systems post-acquisition, PM-Design friction, pressure to ship agentic AI workflows that actually convert, or scaling a senior IC/manager bench) that this hire is really being brought in to fix?
  2. **Counterparty Role Swap & Ring 2 Unwatched Regulator (`claude-creativity` + `ogiberstein`):** Step into each interviewer's exact shoes. What internal metric or executive pressure regulates *their* success over the next 6 months, and how does Sudeep make them win?
  3. **Combinatorial Fusion & Ring 3 Cross-Domain Hook (`claude-creativity` + `ogiberstein`):** Combine Sudeep's enterprise UI/UX leadership scale (Salesforce/Amazon pedigree) with hands-on AI/agentic systems execution into a "category-of-one" positioning narrative (suppressing generic Ring 0/1 design-leadership clichés).
  4. **Inversion Pre-Mortem (`lateral-thinking`):** Identify the top 2 traps or objections a panelist might raise (e.g., scope mismatch, hands-on vs. org-management balance) and pre-wire the exact counter-story.

---

## 3. Interview Dossier Structure (`Antigravity-Data\Sweep-Docs\Interviews\YYYY-MM-DD-<company>-interview-dossier.html` + `.md`)

Generate a self-contained visual **`.html` dossier** (and companion `.md` state), plus update `.state/shyamal-graph/`:

### 1. Loop Snapshot, Epistemic Fact Check & Cross-Domain Calendar Check
- **Company, Role & Level (`[EXTRACTED]`):** Verified title, scope, reporting line, and location/hybrid terms.
- **Schedule & Panel:** Exact dates, times (IST + interviewer timezone), video links, and calendar conflict check.
- **Settled vs. Open Logistics:** `FYI, settled: ...` vs. `Action needed: ...`.

### 2. Company Deep-Dive & Negative Space Org Diagnosis
- **Business Momentum & AI/Product Bets (`[EXTRACTED]`):** What drives revenue and strategic urgency right now.
- **Negative Space Diagnosis (`[INFERRED]`):** The unspoken pain point behind the JD and where a senior UX/Product Design leader creates immediate 90-day leverage.

### 3. Interviewer Profiles, Role-Swap Lenses & How to Land It
For each interviewer on the panel:
- **Background & Ownership (`[EXTRACTED]`):** Tenure, prior companies, remit.
- **Role-Swap Lens & Unwatched Regulator (`[INFERRED]`):** What they are measured on (Design Craft & AI Velocity / PM Outcome Partnership / Eng Feasibility & Platform / Exec Org Building) and what they fear getting wrong in this hire.
- **How to Land It With Them:** Specific angle, vocabulary, and peer-level hook.

### 4. Story & Portfolio Mapping + Inversion Objection Shields
- Map 4-6 of Sudeep's strongest real wins to specific panelist lenses (`[Story Headline] -> [Metric/Outcome] -> [Deploy with Interviewer X]`).
- **Pre-Mortem Objection Shields:** Top 2 likely tough questions + crisp, non-defensive framing.

### 5. High-Altitude Questions to Ask Them (Concept-Fanned)
- 3-4 sharp, peer-level questions tuned to each interviewer's Role-Swap lens (zero generic HR questions).

### 6. Compensation Guardrails, Transparency Log & Outbound Drafts (Not Sent)
- Numbers discussed so far + guardrails from `self/stance.md` + **`Skipped on purpose:`** 1-line Ponytail Transparency Log.
- Ready-to-review reply to the recruiter (`To`, `Subject`, `Body`: **Not Sent**), scrubbed via the **Two-Pass `ai-tells.md` Engine** (zero em dashes).
