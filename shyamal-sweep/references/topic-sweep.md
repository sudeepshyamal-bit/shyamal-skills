# Playbook 4: General Topic / Person Sweep, Graph Refresh & Tracker Audit (`topic-sweep.md`)

Loaded when Sudeep invokes `/shyamal-sweep <topic or person>` for any deep personal research, project synthesis, property/vendor/legal audit, or recurring tracker refresh outside strict Finance, Holiday, or Interview playbooks.

> [!CAUTION]
> **STRICT NO-SEND RULE**
> Never send any email or message directly. Always display any proposed outbound email or message (`To`, `Cc`, `Channel`, `Subject`, `Body`) in the dossier and chat preview for Sudeep's review first.

---

## 1. Wave 0 & Wave 1: Graph-First Baseline & Parallel Sweep
1. **Wave 0 (`GRAPH_REPORT.md` + Local Baseline):**
   - Read `.state/shyamal-graph/GRAPH_REPORT.md` first (`<1,200 tokens`) and check `c:\Users\sudee\OneDrive\Documents\Antigravity-Data\` for existing `.md` or `.csv` files matching `<topic or person>` (never read back large `.html` files to extract facts).
   - If a prior `last_swept` watermark exists for the topic, run a **Delta Sweep (`after:<last_swept - 2d>`)** unless `--full` is requested.
2. **Wave 1 Parallel Queries Across Connected Sources:**
   - **Gmail (`gmail`, `--max-results 25`):** `query: "<topic or person email/name>"` across the delta window (or 180d/all-time for initial sweeps).
   - **Notion (`notion-api`) & Google Drive (`gdrive`, `gdocs`, `gsheets`):** Search matching pages, trackers, spreadsheets, and PDFs.
   - **Google Calendar (`gcalendar`):** Past and upcoming events involving `<topic or person>`.
   - **Web Search (`search_web`):** External facts, regulations, or organizational context when relevant.

---

## 2. Wave 2: Full-Read Resolution, Epistemic Tagging & Lateral Synthesis
- Read every matched Gmail thread to the **last message** (`gmail threads get`). Log already-settled items as `FYI, settled: <what> (<who>, <date>)`.
- Tag all extracted facts and relationships per `references/graphify-engine.md`: **`[EXTRACTED]`** (`1.0`), **`[INFERRED]`** (`0.7-0.99`), or **`[AMBIGUOUS]`** (`<0.7`).
- Run `fact-check.md` on Sudeep's supplied claims, plus check **Negative Space** (what is missing/unspoken), **Ring 2 Unwatched Regulators**, and **`ponytail-audit` (`Cut / Consolidate / Automate`)** from `shyamal-assistant/references/thinking-models.md`.

---

## 3. Refresh Mode Rules (When Updating an Existing Doc, Sheet, Notion Page, or Local Tracker)
- **Update & Add, Never Delete:**
  - Update stale lines in place with newer dates, numbers, and `[EXTRACTED]` statuses.
  - Merge duplicate findings into the existing item rather than creating clutter.
  - Append new items in priority order using native checkboxes (`- [ ]`).
  - **Never delete lines Sudeep wrote**, and **never overwrite his manual Notes section/column**.
- **Topic Labels in Title Case:** Format tracker bullets cleanly as `**Topic Label:** concise outcome or next step with owner and date`.

---

## 4. Output Document Structure (`Antigravity-Data\Sweep-Docs\Topics\YYYY-MM-DD-<slug>.html` + `.md`)

Generate a self-contained visual **`.html` dossier** (and companion `.md` state), plus update `.state/shyamal-graph/` (`GRAPH_REPORT.md`, `graph.json`, `graph.html`):

1. **Executive Summary, Fact Check & God Node Connections:** Top takeaways, verification of Sudeep's claims (`[EXTRACTED] / [INFERRED] / [AMBIGUOUS]`), and how this topic links to other clusters in `GRAPH_REPORT.md`.
2. **Chronological Timeline & Current State:** Verified sequence across Gmail, Notion, Drive, and Local files with exact dates and citations.
3. **Key Numbers, Documents & Negative Space Gaps:** Direct links to authoritative files/threads + any omitted constraint or statutory/contractual blind spot spotted via Negative Space.
4. **`ponytail-audit` Simplification Backlog (`Cut / Consolidate / Automate`):** What to drop, merge, or pre-empt to reduce friction.
5. **Close the Loop (Open Asks & Next Steps):**
   - `- [ ] **<Item> (`[EXTRACTED / AMBIGUOUS]`):** <status, owner, due date>`
   - `FYI, settled: <resolved items>`
6. **Recommendations, Sequencing & Transparency Log:** Concrete next steps grounded in `self/stance.md` + **`Skipped on purpose:`** 1-line Ponytail Transparency Log.
7. **Ready-to-Review Outbound Drafts (Not Sent):** Any proposed email or message (`To`, `Channel`, `Subject`, `Body`), scrubbed through the **Two-Pass `ai-tells.md` Engine** (zero em dashes).
