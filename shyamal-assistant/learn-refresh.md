# Learn and Refresh-Relationships (`learn-refresh.md`)

## 1. `/shyamal-assistant learn` (Post-Conversation / Post-Decision Capture)
1. Read `c:\Users\sudee\OneDrive\Documents\Antigravity-Data\.state\shyamal-assistant\last-session.md`.
2. If `last-session.md` is missing, say so and ask Sudeep to paste what he actually sent or decided. Otherwise ask three short questions in one message:
   - **What did you actually say or do?**
   - **How did it land?**
   - **What would you do differently next time?**
3. Write `C:\Users\sudee\.gemini\config\skills\shyamal-assistant\history\YYYY-MM-DD-<who-or-topic>.md` with frontmatter (`date`, `counterparty`, `mode`, `outcome: win | draw | loss`), the three answers, and the original draft/recommendation.
4. If Q3 reveals a new personal principle, boundary/red line, counterparty archetype, altitude rule, or voice habit, propose a one-line patch to `self/stance.md` (or `self/voice.md` for a voice habit) and ask Sudeep to confirm before writing.

---

## 2. `/shyamal-assistant refresh-relationships`
Builds or updates personal relationship cards in `C:\Users\sudee\.gemini\config\skills\shyamal-assistant\relationships\<category>\<name>.md` using read-only signals from Gmail, Calendar, Notion, and local files.

### Categories (`<category>`)
- `inner-circle/` (family, close friends, travel companions)
- `collaborators/` (side-project partners, creative collaborators, peers)
- `recruiters-career/` (recruiters, hiring managers, interview contacts, mentors)
- `vendors-advisors/` (CA/financial advisors, banks, doctors, travel operators, recurring service providers)

### Steps
1. Identify recurring contacts from:
   - Any specific person(s) Sudeep named in the command (e.g., `/shyamal-assistant refresh-relationships <name>`), OR
   - If run without arguments: Gmail threads with 3+ back-and-forth messages in the last 60 days (`gmail messages list`), plus recurring 1:1 Calendar attendees (`gcalendar`) in the last 60 days.
2. For each person, pull their recent Gmail thread subjects/topics, Calendar cadence, and any mentions in Notion or `Antigravity-Data`.
3. Write or update `C:\Users\sudee\.gemini\config\skills\shyamal-assistant\relationships\<category>\<slug>.md`:
   ```markdown
   ---
   name: <Full Name>
   email: <email>
   category: inner-circle | collaborators | recruiters-career | vendors-advisors
   tier: INNER_CIRCLE | COLLABORATOR | EXTERNAL_FORMAL | VENDOR_OFFICIAL
   updated: YYYY-MM-DD
   ---

   **What they care about / Context (signal-derived):**
   - <bullet>

   **Communication style:**
   - <channel pref, message length, responsiveness>

   **Recent topics & open loops (last 60d):**
   - <bullet>

   **Cadence with Sudeep:**
   - <e.g., monthly check-in, active interview loop, trip group>

   **Sudeep's notes (manual: NEVER overwrite across refreshes):**
   - <free-form preserved across updates>
   ```
4. **Never overwrite** the `Sudeep's notes` section when refreshing an existing file.
