# Playbook 1: Financial Sweep, Knowledge Graph & Master Plan (`finance-sweep.md`)

Loaded when Sudeep invokes `/shyamal-sweep finance [topic]` or asks to map his revenue streams, audit expenses/subscriptions/loans, review investments, or refresh his personal financial master plan.

> [!CAUTION]
> **STRICT NO-SEND & PRIVACY RULE**
> - Never send any email or message to a bank, CA, advisor, or builder directly. Always display proposed emails (`To`, `Subject`, `Body`) in the dossier and chat preview first.
> - Redact sensitive account numbers in top-level headings (`XXXX-2846`, `XXXX-0026`) and tag every figure with its Graphify provenance badge (`[EXTRACTED]`, `[INFERRED]`, `[AMBIGUOUS]`) and source citation.

---

## 1. Wave 0 & Wave 1: Graph-First Delta or Full Discovery
1. **Wave 0 (`GRAPH_REPORT.md` + Local Baseline):**
   - Read `c:\Users\sudee\OneDrive\Documents\Antigravity-Data\.state\shyamal-graph\GRAPH_REPORT.md`, `Financial Planning/Arvind-Unified-Master-Plan.csv`, and the latest `.md` file in `Sweep-Docs/Finances/` (never parse large `.html` files for input data).
   - If `last_swept` exists and `--full` was not requested, run a **Delta Sweep (`after:<last_swept - 2d>`)** across Gmail and Drive to capture new remittances, loan disbursements, statements, or tax notices at 75% lower token cost.
2. **Wave 1 Parallel Queries (Scoped to Delta Window, or `newer_than:365d` on Full Sweep):**
   - **Gmail (`gmail`, `--max-results 25`):**
     - *Inflows & Remittances:* `"(salary OR payslip OR credited OR payout OR dividend OR RSU OR Morgan Stanley OR P0021 OR FIRC OR rent OR bonus)"`
     - *Loans, Property & Outflows:* `"(Arvind OR Forest Trails OR BOI OR Bank of India OR Pre-EMI OR EMI OR disbursement OR demand note OR Form 26QB OR TDS OR insurance OR SIP OR Scripbox OR HDFC OR Zerodha OR ITR OR advance tax OR CA)"`
   - **Google Drive / Sheets / Docs (`gdrive`, `gsheets`, `gdocs`):** `finance`, `budget`, `salary`, `bonus`, `projection`, `Arvind`, `tax`, `ITR`.
   - **Notion (`notion-api`) & Calendar (`gcalendar`):** Search financial trackers and next-90-day renewal/tax/disbursement reminders.

---

## 2. Wave 2: Deep Verification, Negative Space & Lateral Stress-Test
- Read matched Gmail threads to the **very last message** (`gmail threads get`) so already-settled items (like BOI Pre-EMI interest explanations or sent P0021 disposal instructions) are logged as `FYI, settled`.
- Tag every number and edge per `references/graphify-engine.md`: **`[EXTRACTED]`** (`1.0`), **`[INFERRED]`** (`0.7-0.99`), or **`[AMBIGUOUS]`** (`<0.7`).
- Run three mandatory analytical checks (`thinking-models.md`):
  1. **Negative Space & Ring 2 Unwatched Regulator Check (`claude-creativity` + `ogiberstein`):** What statutory clock or compliance step is *missing* from the email threads? (e.g., 30-day Form 26QB 1% TDS filing on property milestones, FIRC collection for Sec 54F audit trails, Dec 15 / Mar 15 Advance Tax on foreign RSU sales, missing demat nominations).
  2. **Inversion Pre-Mortem (`lateral-thinking`):** Assume a liquidity crunch or tax dispute happens 6 months from now; identify the 2-3 exact timing or margin bottlenecks that would trigger it and build guardrails today.
  3. **`ponytail-audit` Financial Simplification (`Delete / Consolidate / Automate`):** Identify idle cash losing yield, redundant accounts/subscriptions, or manual bank follow-ups that can be pre-empted in one move.

---

## 3. Dossier Structure (`Antigravity-Data\Sweep-Docs\Finances\YYYY-MM-DD-<slug>.html` + `.md`)

Generate a self-contained visual **`.html` dashboard** (for Sudeep) and companion **`.md` file** (for future low-token agent reads), plus update `.state/shyamal-graph/` (`GRAPH_REPORT.md`, `graph.json`, `graph.html`):

### 1. Executive Snapshot, Premise Check & Graphify God Nodes
- **Fact & Epistemic Check:** Verified `[EXTRACTED]` numbers vs. corrected `[OFF/OUTDATED]` or `[AMBIGUOUS]` items.
- **God Nodes & Surprising Cross-Domain Bridges:** Highlight how inflows, RSU sales, loan tranches, and tax shields connect across communities (`C1 Banking <-> C2 Property <-> C3 Equity/Tax`).

### 2. Current Revenue & Inflow Map
| Stream / Node | Frequency | Verified Amount & Epistemic Tag | Latest Date & Source | Role in Master Plan |
| :--- | :--- | :--- | :--- | :--- |
| Salary / Bonus / RSU Sales / Spouse / Future Rent | Monthly / Annual / Milestone | Exact figure + `[EXTRACTED]` or `[INFERRED]` | e.g., `Gmail Nov 14` / `Master CSV` | Exact allocation & guardrails |

### 3. Outflows, Loans, Milestone Ledger & Protected Wealth Engines
- **Active Loans & Construction Milestones** (disbursed balance, Pre-EMI interest, borrower margin math, self-funded vs. bank-funded milestone schedule).
- **Protected Wealth Engines** (Scripbox ₹1L/mo SIP guardrail, HDFC ₹1L/mo RD sinking fund, Zerodha `JET027`, Insurance auto-debits).

### 4. `ponytail-audit` Simplification Backlog (`Cut / Consolidate / Automate`)
- **Cut / Cancel:** Unused subscriptions, avoidable interest/penalties, or unnecessary credit lines.
- **Consolidate / Ring-Fence:** Idle remittance cash to sweep into 60-day FDs/Liquid funds maturing on milestone dates.
- **Automate / Pre-Empt (Value-Chain Flip):** Standing instructions or upfront FEMA/FIRC emails that eliminate bank suspense delays.

### 5. Close the Loop: Open Actions, Negative Space & Inversion Guardrails
- `- [ ] **[Action Label] (`[EXTRACTED / AMBIGUOUS]`):** <what needs to happen, amount, statutory due date, owner>`
- `FYI, settled: <recently closed/resolved items with date and source>`

### 6. Sequenced Action Plan & Transparency Log
- **Immediate 7-Day Actions** and **Medium-Term Strategy** grounded in `self/stance.md`.
- **`Skipped on purpose:`** 1-line Ponytail Transparency Log naming what complex financial structuring was intentionally skipped and why.

### 7. Ready-to-Review Outbound Drafts (Not Sent)
Full preview blocks (`To`, `Cc`, `Channel`, `Subject`, `Body`) scrubbed through the **Two-Pass `ai-tells.md` Engine** (zero em dashes).
