# Draft-Reply (`reply.md`)

Loaded for pasted messages/emails/threads, `"reply to"`, `"respond to"`, `"what should I say to"`. Follows the Ironclad Outbound Lock in `SKILL.md` (draft preview only, never auto-send).

---

## 1. Channel Detection
- **Email headers** (`From:`, `To:`, `Subject:`, `>` quotes, recruiter/bank/vendor formatting) -> **Email (Gmail)**.
- **Short conversational text, timestamps, WhatsApp/SMS style** -> **WhatsApp / Direct Message** (strictly conversational: no subject line, no formal numbered lists, no sign-off name, no 4+ sentence unbroken wall of text).
- **LinkedIn / Recruiter InMail cues** -> **LinkedIn / External Formal**.
- **Raw question with no pasted message** -> Conversational advice (or route to `decide-strategy.md`).

---

## 2. Token-Smart Flow

0. **Graph-First Fact & Context Check (`GRAPH_REPORT.md` + `fact-check.md`):**
   - Read `.state/shyamal-graph/GRAPH_REPORT.md` first. If the counterparty, account number, loan, or booking is already `[EXTRACTED]` in the graph, reuse those verified facts immediately and limit any Gmail check to `newer_than:7d --max-results 5`.
   - If Sudeep supplied specific claims (`"tell them I paid on Nov 3"`, `"tell her Tuesday 4pm works"`), verify per `fact-check.md` and print a `Fact check` block above the drafts when anything is `Off`, `Outdated`, or `AMBIGUOUS`.
1. **Mandatory Outbound Envelope (Human-in-the-Loop Visibility):**
   ```markdown
   **Outbound Preview (Draft Only: Will Not Send)**
   - **To:** <Name / Email / Handle>
   - **Cc:** <None or list>
   - **Channel:** <Gmail / WhatsApp / LinkedIn / etc.>
   - **Subject:** <Subject line if Email>
   ```
2. **Produce 3 Genuinely Distinct Options in Sudeep's Voice (`self/voice.md`):**
   - **Completeness & Proportionality Law:** Every option must include **100% of the mandatory data points, account numbers, purpose codes, and declarations** required so there is zero back-and-forth, formatted like a real human (never ASCII divider bars `----` or empty form rows).
   - **Option A / Direct (Ponytail Rung 6 Minimum-Viable):** Crisp, matter-of-fact, straight to the point. Contains every required data point with zero extra framing.
   - **Option B / Warmer + Counterparty Role Swap (`claude-creativity`):** Same complete data points + natural human warmth tuned to the recipient's exact lens/incentive (e.g., acknowledging why you are sharing disposal details upfront so their compliance check is easy).
   - **Option C / Concept-Fanned & Sequence-Flipped (`lateral-thinking` + `claude-creativity`):** Same complete data points + climbs one level up (**Concept Fan / Synthesis / Value-Chain Flip**) to preempt the *next* two rounds of back-and-forth in a single move (e.g., locking the immediate release while simultaneously requesting the FIRC PDF or confirming the next milestone split).
3. **No Blocking Picker:** Print A, B, and C as three fenced blocks in the final message and end the turn. Under each block add one italic line: `*tier: <tier>, register: <descriptor>, lens: <Ponytail Direct | Role Swap | Concept-Fanned>*`.
   - For Gmail: `Reply A, B, or C to save it to your Gmail Drafts (nothing will be sent), or tell me what to tweak.`
   - For WhatsApp / LinkedIn / other: `Pick A, B, or C to copy, or tell me what to tweak.`
4. **When Sudeep Replies A, B, or C for an Email:**
   - Run `gmail drafts create` with the chosen text, recipient, subject, and thread ID. **Never run `gmail send` or `gmail reply`.**
   - Confirm in one line: `Saved to Gmail Drafts (Draft ID: <id>) for <To>. Review and send from Gmail when ready.`

---

## 3. Two-Pass Quality & Voice Gate (Run Before Returning)
1. **Voice & Tier Match (`self/voice.md`):** Match opener (`"Hi <Name>,"` / `"Hey <Name>, "` with capital letter after comma in chat), punctuation (`!!` only in warm personal/collaborator tiers, zero em dashes anywhere), and closer.
2. **Stance Check (`self/stance.md`):** Calm, non-defensive under friction; ends on a concrete next step/ask with owner and timeline.
3. **Two-Pass `ai-tells.md` Scrub:**
   - *Pass 1:* Replace Tier 1A/1B words, break Tier 2 clusters, strip `-ing` participle tails, copula avoidance (`serves as` -> `is`), and Rule-of-Three triads.
   - *Pass 2:* Verify Pass 1 edits did not introduce stiff transitions or uniform paragraph lengths, and confirm all protected phrases in `ai-tells.md` §4 remain untouched.
