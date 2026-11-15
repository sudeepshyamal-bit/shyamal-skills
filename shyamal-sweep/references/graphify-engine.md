# Graphify Personal Knowledge Graph Engine (`graphify-engine.md`)

Adapted from `safishamsi/graphify` (`Graphify-Labs/graphify`) for Sudeep's Personal OS. Turns scattered emails, spreadsheets, docs, calendar blocks, and local files into a persistent, queryable knowledge graph stored in `c:\Users\sudee\OneDrive\Documents\Antigravity-Data\.state\shyamal-graph\`.

---

## 1. The Three Graph Artifacts

1. **`GRAPH_REPORT.md` (Agent Orientation Report, capped at ≤120 lines / ~1,200 tokens):**
   - **Rule #1 (Graph-First Short-Circuit):** Both `/shyamal-assistant` and `/shyamal-sweep` MUST read `GRAPH_REPORT.md` **before** running broad searches across Gmail, Drive, or Notion.
   - Contains: **Watermark Manifest (`last_swept`)**, **God Nodes (Top Centrality Hubs)**, **5 Leiden Community Clusters (`C1–C5`)**, **Surprising Cross-Community Bridges**, **Active Open Loops**, and **Suggested Questions**.
2. **`graph.json` (Portable Structured Node & Edge Database):**
   - Stores machine-queryable `nodes` (`id`, `label`, `community`, `type`, `is_god_node`, `degree`, `attributes`) and `edges` (`source`, `target`, `relation`, `confidence_tag`, `confidence_score`, `surprise_flag`, `evidence`).
3. **`graph.html` (Interactive Visual Knowledge Graph):**
   - Self-contained browser dashboard allowing Sudeep to filter by Community (`C1–C5`), highlight God Nodes, inspect `[EXTRACTED] / [INFERRED] / [AMBIGUOUS]` edges, and search across all connected entities.

---

## 2. Epistemic Edge & Fact Tagging (`EXTRACTED`, `INFERRED`, `AMBIGUOUS`)

Every relationship in the graph and every key claim in a `/shyamal-sweep` HTML dossier carries one of Graphify's three epistemic provenance tags:

| Tag | Score Band | Definition & When to Assign | Visual Rendering |
| :--- | :--- | :--- | :--- |
| **`[EXTRACTED]`** | `1.00` | Deterministically parsed from an authoritative primary record (bank statement, UTR confirmation, signed sanction letter, PNR ticket, payslip, or explicit email confirmation). | Solid green badge (`EXTRACTED`) |
| **`[INFERRED]`** | `0.70 – 0.99` | Synthesized across 2+ sources via domain reasoning (e.g., linking a Morgan Stanley RSU trade confirmation to an upcoming builder demand note window or tax deadline). Must explicitly state the bridge logic. | Dashed blue badge (`INFERRED`) |
| **`[AMBIGUOUS]`** | `< 0.70` | Referenced in one place without verification, or conflicting across two sources (e.g., a statutory TDS Form 26QB requirement where no challan receipt was found in Gmail). Automatically promoted to `Open Loops` for Sudeep's 1-line confirmation. | Amber/red badge (`AMBIGUOUS`) |

---

## 3. Watermark Delta-Sweeps (`--update` Token-Saving Protocol)

To avoid burning 50,000+ tokens re-crawling 365 days of Gmail on every sweep:
1. **Check the Watermark First:** Read `last_swept` for the target domain in `GRAPH_REPORT.md` (`Finances`, `Holidays`, `Interviews`, `Topics`).
2. **Run a Delta Sweep by Default:**
   - If a baseline `.md` dossier and `last_swept` date exist, scope Wave 1 Gmail and Drive queries to **`after:<last_swept - 2 days>`** (the 2-day overlap prevents timezone boundary misses).
   - Read the existing `.md` dossier (never parse the `.html` file for data extraction, as `.html` is 65% CSS/DOM markup) and merge the delta findings in place.
3. **Full Historical Rebuild (`--full`):**
   - Only run a full 180-to-365-day sweep when (a) no prior `last_swept` watermark exists for that topic/company/trip, or (b) Sudeep explicitly passes `--full` or asks to rebuild from scratch.

---

## 4. God Nodes, Communities & Surprising Bridges

Whenever `/shyamal-sweep` finishes Wave 2 verification, run this 4-step graph synthesis before writing Step 3 outputs:

1. **Community Assignment (`C1–C5`):**
   - `C1: Banking & Remittances` | `C2: Property & Debt` | `C3: Equity, Wealth & Tax` | `C4: Family & Travel` | `C5: Career & Creative IP`.
2. **God Node & Blast-Radius Check:**
   - Identify which high-degree hubs (`IDFC_2846`, `ARVIND_B25`, `BOI_LOAN_0026`, `CRM_COMP`, `WEALTH_CORE`, or a new Trip/Company hub) are touched by the sweep.
   - Trace **2-hop paths** (`Node A -> God Node -> Node B`) to check the **Blast Radius**: e.g., if a travel window or interview loop shifts, does it collide with an advance tax date, RSU vest window, or builder milestone?
3. **Surprising Connections (`surprise_flag: true`):**
   - Flag any edge that bridges two different Communities (`C_i <-> C_j`) and reveals a non-obvious dependency, timing collision, or tax/compliance hook. Highlight these in the dossier's **God Nodes & Cross-Domain Bridges** callout.
4. **Update `.state/shyamal-graph/`:**
   - Update `GRAPH_REPORT.md` (keeping it ≤120 lines), `graph.json`, and `graph.html` with any newly verified nodes, updated balances/statuses, closed loops, and the new `last_swept` date.
