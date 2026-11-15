# Playbook 2: Holiday & Travel Sweep (`holiday-sweep.md`)

Loaded when Sudeep invokes `/shyamal-sweep holiday <destination/trip>` or asks to plan a vacation/trek/trip, check bookings, align calendar windows, or build/refresh an itinerary and packing plan.

> [!CAUTION]
> **STRICT NO-SEND RULE**
> Never send any email or message to airlines, hotels, safari/trek operators, or travel companions directly. Always display draft inquiries or confirmations (`To`, `Channel`, `Subject`, `Body`) for Sudeep's review first.

---

## 1. Wave 0 & Wave 1: Graph-First Baseline & Parallel Discovery
1. **Wave 0 (`GRAPH_REPORT.md` + Local Trip Docs):**
   - Read `.state/shyamal-graph/GRAPH_REPORT.md` and check `c:\Users\sudee\OneDrive\Documents\Antigravity-Data\` for existing trip folders or markdown plans (e.g., `Pench-Packing\Pench-Trek-Packing-Plan.md`). Read `.md` files first; never parse large `.html` files to extract baseline facts.
   - If refreshing an existing trip doc, use its `last_swept` date to run a **Delta Sweep (`after:<last_swept - 2d>`)** in Gmail while preserving 100% of Sudeep's custom packing bullets and notes.
2. **Wave 1 Parallel Queries:**
   - **Google Calendar (`gcalendar`):** Pull events across the travel window (or next 90 days) to verify free multi-day blocks, public holidays, school/family commitments, and cross-domain collisions (e.g., an interview loop or financial deadline falling mid-trip).
   - **Gmail (`gmail`, `--max-results 25`):** `query: "(<destination> OR flight OR IndiGo OR Air India OR Akasa OR PNR OR MakeMyTrip OR Booking.com OR Airbnb OR Agoda OR safari OR permit OR resort OR hotel OR itinerary OR trek OR train OR IRCTC)"`
   - **Notion & Google Drive (`notion-api`, `gdrive`, `gdocs`, `gsheets`):** Search `<destination>`, `trip`, `holiday`, `itinerary`, `packing`.
   - **Web Search (`search_web`):** Seasonality/weather for the exact dates, safari/permit lead times, gate/zone logistics, and baggage/entry rules.

---

## 2. Wave 2: Resolution Check, Negative Space & `ponytail-audit` Buffer Check
- Read every matched Gmail booking thread to the **last message** (`gmail threads get`) and tag each leg with its Graphify provenance badge:
  - **`Confirmed [EXTRACTED]`** (PNR / Voucher ID verified)
  - **`Pending / Waitlisted [INFERRED]`**
  - **`Missing / Unverified [AMBIGUOUS]`**
- **Negative Space & Inversion Pre-Mortem (`claude-creativity` + `lateral-thinking`):**
  - What is missing between the booked legs? (e.g., airport-to-resort transfer gap after sunset, forest gate entry ID mismatch, cash-only tip/gypsy rules, or a missing return check-in window).
- **`ponytail-audit` Buffer & Un-Pack Audit (`Family first!!` Guardrail):**
  - Audit the itinerary against `self/stance.md` Rule #4: flag and cut over-packed back-to-back transitions so the family has real rest/buffer windows.

---

## 3. Master Travel Plan Structure (`Antigravity-Data\Sweep-Docs\Holidays\YYYY-MM-DD-<dest>-plan.html` + `.md`)

Generate/refresh the visual **`.html` dashboard** (and update the existing `.md` trip plan in place without deleting Sudeep's notes), plus update `.state/shyamal-graph/`:

### 1. Trip Snapshot, Calendar Alignment & Cross-Domain Bridges
- **Verified Window & Party:** Dates, duration, travel companions, and calendar conflict check.
- **Fact & Epistemic Check:** Discrepancies spotted between assumed timings and `[EXTRACTED]` tickets/vouchers.
- **Cross-Domain Bridges (`graphify`):** Any financial, tax, or work item overlapping the travel window that should be pre-cleared before departure.

### 2. Bookings & Logistics Ledger (Close the Loop)
| Leg / Item | Status & Epistemic Tag | Provider & Ref / PNR | Verified Dates & Timings | Action Needed / Owner |
| :--- | :--- | :--- | :--- | :--- |
| Flights / Trains / Stays / Safaris / Transfers | `Confirmed [EXTRACTED]` or `Open [AMBIGUOUS]` | Exact PNR / Voucher / Operator | Dep/Arr or Check-in/Slot | Concrete next step + deadline |

### 3. Day-by-Day Itinerary (Paced with Buffer Windows)
- Realistic daily flow with transit times, meal/rest buffers, and activity slots.

### 4. `ponytail-audit` Simplification & Pre-Trip Negative Space
- **Un-Pack / Simplify:** Over-scheduled blocks or redundant gear to drop.
- **Pre-Departure Negative Space (Inversion Safeguards):** Permits, original IDs, offline maps, medical kit, or home/financial checks to lock 48h prior.

### 5. Tailored Packing & Prep Checklist
Organized with clickable checkboxes (`- [ ]`) across Documents & IDs, Weather-Tuned Layers, Trek/Safari Gear & Electronics, Meds & Toiletries, and Pre-Departure Checks (preserving all of Sudeep's custom items).

### 6. Sequenced Next Steps, Transparency Log & Outbound Drafts (Not Sent)
- Ordered list of time-sensitive bookings/confirmations + **`Skipped on purpose:`** 1-line Ponytail Transparency Log.
- Full preview (`To`, `Channel`, `Subject`, `Body`) for any operator/hotel email or WhatsApp message, scrubbed via the **Two-Pass `ai-tells.md` Engine** (zero em dashes).
