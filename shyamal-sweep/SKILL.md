---
name: shyamal-sweep
description: Sudeep's deep multi-source intelligence, knowledge-graph, and planning skill (replaces shyamal-prep), enriched with graphify (persistent Personal Knowledge Graph, Watermark Delta-Sweeps, God Nodes, Surprising Bridges, and EXTRACTED/INFERRED/AMBIGUOUS epistemic tags), ponytail (ponytail-audit Cut/Consolidate/Automate backlog & Transparency Log), lateral-thinking (Concept Fan, Inversion Pre-Mortem, 4-Ring discovery), claude-creativity (Negative Space, Role Swap, Synthesis, Time Travel), and avoid-ai-writing (2-pass engine). Match whenever Sudeep asks to plan or review his finances/revenue/loans, plan a holiday/trip/packing/itinerary, research an organisation or prep for an interview, or sweep his data (Gmail, Notion, Drive, Docs, Sheets, Calendar, local files) on any topic. IMPORTANT: when matched automatically from a natural-language request (where Sudeep did NOT explicitly type /shyamal-sweep), ALWAYS check with Sudeep first ("Would you like me to invoke /shyamal-sweep for this?") and wait for his yes before running the sweep. Strictly enforces the Human-in-the-Loop Outbound Rule: never sends any email or message directly.
---

# /shyamal-sweep

*(Replaces and deprecates `/shyamal-prep`.)*

Builds a source-verified `.html` visual dashboard (plus compact `.md` state and updated `.state/shyamal-graph/` knowledge graph) by sweeping across Sudeep's connected personal sources in parallel: **Personal Knowledge Graph (`GRAPH_REPORT.md`)**, **Gmail**, **Notion**, **Google Drive**, **Google Docs**, **Google Sheets**, **Google Calendar**, **Local Workspace (`Antigravity-Data`)**, and **Web Search**.

> [!IMPORTANT]
> **STEP 0: AUTO-DETECTION & INVOCATION CONFIRMATION GATE**
> - **Ask before invoking (unless explicitly called via `/shyamal-sweep`):** If Sudeep did **not** explicitly type `/shyamal-sweep` in his prompt, **pause before running any Wave 1 searches** and ask in one short line:
>   *"Would you like me to invoke `/shyamal-sweep` (`<mode>`) to sweep your Gmail, Drive, Calendar, Notion, and local files for this?"*
> - Proceed only once he confirms (or immediately if he typed `/shyamal-sweep`).

> [!CAUTION]
> **IRONCLAD OUTBOUND RULE: HUMAN IN THE LOOP ALWAYS**
> - **Never send an email, reply, forward, or calendar invite directly from `/shyamal-sweep`.**
> - Any follow-up emails or messages discovered during a sweep (to a recruiter, bank RM, credit officer, CA, hotel, or safari operator) MUST be displayed in a **`Ready-to-Review Outbound Drafts (Not Sent)`** section showing `To`, `Cc`, `Channel`, `Subject`, and `Body`. Only create an unsent Gmail Draft (`gmail drafts create`) if Sudeep asks.

---

## Core Operating & Token-Smart Rules

1. **Graph-First & Watermark Delta-Sweeps (`references/graphify-engine.md`):**
   - Always read `c:\Users\sudee\OneDrive\Documents\Antigravity-Data\.state\shyamal-graph\GRAPH_REPORT.md` (`<1,200 tokens`) **first** in Wave 0.
   - **Delta Sweep by Default (Saves ~75% Tokens):** If `GRAPH_REPORT.md` has a `last_swept` date and an existing `.md`/`.csv` baseline for the domain, scope Gmail/Drive queries to **`after:<last_swept - 2d>`** (`--max-results 25`) and merge the new delta signals into the baseline. Run a full 180-to-365-day historical sweep only when no baseline exists or Sudeep passes `--full`.
2. **Agent Reads `.md`/`.csv`, Human Reads `.html` (Token Guardrail):**
   - Styled `.html` dashboards are ~65% CSS/DOM markup. During Refresh Mode, **never read a large `.html` file to extract data**; read `GRAPH_REPORT.md` and the companion `.md` or `.csv` file, then regenerate/refresh both the `.md` state and the visual `.html` dashboard.
3. **Refresh Mode (Update & Add, Never Delete Sudeep's Notes):**
   - When updating an existing tracker, Google Doc, Sheet, Notion page, or local file, update stale facts in place, mark settled items, append new findings, and **never delete Sudeep's manual notes or custom bullets**.
4. **Fact-Check + Graphify Epistemic Tags (`fact-check.md`):**
   - Validate every figure, date, and status against live sources and tag key findings with **`[EXTRACTED]`** (`1.0` primary record), **`[INFERRED]`** (`0.7-0.99` cross-source synthesis), or **`[AMBIGUOUS]`** (`<0.7` unconfirmed/conflicting).
5. **Resolution Check & Negative Space (`claude-creativity`):**
   - Read matched Gmail threads to the **very last message** (`gmail threads get`). Log already-resolved items as `FYI, settled: <what> (<who>, <date>)`.
   - Explicitly check **Negative Space & Ring 2 Unwatched Regulators**: surface omitted statutory deadlines (e.g., 30-day Form 26QB TDS windows), clearance lags, or unspoken constraints that nobody in the thread mentioned.
6. **`ponytail-audit` Simplification Backlog & Transparency Log:**
   - Every sweep includes a ranked **`Cut / Consolidate / Automate`** section (`ponytail-audit`) and ends its strategy section with a 1-line **`Skipped on purpose`** Transparency Log.
7. **Voice & Two-Pass `ai-tells.md` Scrub:**
   - Read `self/voice.md`, `self/stance.md`, and `ai-tells.md` (in `shyamal-assistant/`). **Zero em dashes (`—` or ` -- `) anywhere** in the HTML dossier, Markdown state, or chat summary.

---

## Invocations & Playbook Routing

| Input / Trigger | Mode | Playbook to Load |
| :--- | :--- | :--- |
| `/shyamal-sweep finance [topic]`, *"plan my finances"*, *"map my revenue stream"*, *"audit my subscriptions/loans/investments"* | **1. Financial Sweep & Plan** | `references/finance-sweep.md` + `references/graphify-engine.md` |
| `/shyamal-sweep holiday <dest>`, *"plan a holiday/trip"*, *"packing/itinerary for <place>"*, *"check my trip bookings"* | **2. Holiday & Travel Plan** | `references/holiday-sweep.md` + `references/graphify-engine.md` |
| `/shyamal-sweep interview <org/role>`, *"interview prep for <company>"*, *"research <org> for my interview"* | **3. Interview & Org Dossier** | `references/interview-sweep.md` + `references/graphify-engine.md` |
| `/shyamal-sweep <topic or person>`, *"sweep everything on <X>"*, *"refresh knowledge graph"* | **4. Topic / Graph Sweep** | `references/topic-sweep.md` + `references/graphify-engine.md` |

Also load `C:\Users\sudee\.gemini\config\skills\shyamal-assistant\fact-check.md` (and `C:\Users\sudee\.gemini\config\skills\shyamal-assistant\references\thinking-models.md` when deep strategic synthesis is required).

---

## Three-Stage Execution Architecture (Every Mode)

### Wave 0 & Wave 1: Graph-First Check + Parallel Discovery Sweep
1. **Wave 0 (Graph & Baseline Read):** Read `.state/shyamal-graph/GRAPH_REPORT.md` and any existing local `.md`/`.csv` baseline in `c:\Users\sudee\OneDrive\Documents\Antigravity-Data\`. Determine whether this is a **Delta Sweep (`after:<last_swept - 2d>`)** or a **Full Sweep**.
2. **Wave 1 (Parallel Queries Across Connected Sources):**
   - **Gmail (`gmail`):** 2-4 targeted queries (`--max-results 25`).
   - **Google Drive / Docs / Sheets (`gdrive`, `gdocs`, `gsheets`):** Search matching spreadsheets, PDFs, and docs.
   - **Notion (`notion-api`):** `API-post-search` and `API-query-data-source`.
   - **Google Calendar (`gcalendar`):** Pull events for the relevant window (`-30d` to `+90d`).
   - **Web Search (`search_web`):** Run for external company intel, travel permits/weather, or tax/statutory rules.

### Wave 2: Deep Read, Resolution Check, Epistemic Tagging & Lateral Audit
- Read the top matched Gmail threads (`gmail threads get`) to the **last message**, plus matched Sheets, Docs, Notion pages, and local files.
- Assign Graphify epistemic tags (`[EXTRACTED]`, `[INFERRED]`, `[AMBIGUOUS]`) and verify Sudeep's claims per `fact-check.md`.
- Run **Negative Space & Ring 2 Regulator Check**, **Inversion Pre-Mortem**, and **`ponytail-audit` (`Cut / Consolidate / Automate`)**.

### Step 3: Write HTML Dossier + Markdown State + Update Knowledge Graph
1. **Primary Deliverable (`.html` Visual Dashboard + `.md` State):**
   - Write the self-contained visual `.html` dashboard (with KPI cards, `[EXTRACTED]/[INFERRED]/[AMBIGUOUS]` badges, **God Nodes & Cross-Domain Bridges** callout, styled tables, clickable checkboxes, **`ponytail-audit` Simplification Backlog**, and copyable outbound draft boxes) to `c:\Users\sudee\OneDrive\Documents\Antigravity-Data\Sweep-Docs\<Category>\<YYYY-MM-DD>-<slug>.html` (and update the companion `.md` file for future low-token agent reads).
2. **Update `.state/shyamal-graph/` (`references/graphify-engine.md`):**
   - Update `GRAPH_REPORT.md` (≤120 lines), `graph.json`, and `graph.html` with newly discovered God Nodes, edges, updated `last_swept` watermarks, and open loops.
3. **Sync Session State:**
   - Write a concise 5-8 line summary to `c:\Users\sudee\OneDrive\Documents\Antigravity-Data\.state\shyamal-assistant\last-session.md` and print the clickable `.html` dossier link + `graph.html` link in chat.
