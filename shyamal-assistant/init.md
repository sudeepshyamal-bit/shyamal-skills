# `/shyamal-assistant init` — Optional Self-Model Deep-Dive & Voice Refresh

_Not required to run the skill (`self/voice.md` and `self/stance.md` are already seeded). Run this whenever Sudeep wants to deepen `self/stance.md` for his personal life or refresh `self/voice.md` from his sent Gmail corpus._

Walk Sudeep through the sections below in order. **Save `self/stance.md` at the end of each section** so a partial interview is always preserved and resumable.

Output directory: `C:\Users\sudee\.gemini\config\skills\shyamal-assistant\self\`

## Before Starting
1. Check `self/stance.md` and `self/voice.md`. Offer:
   `"I see your seeded voice.md and stance.md. Want to walk through the personal stance questions (Sections 2–5), refresh voice.md from your recent Sent emails, or pick a specific section?"`
2. Keep the tone conversational, not a rigid survey. Drill once when an answer is generic (`"Give me a real example from the last few months"`).

---

## Section 1 — Voice & Tone (Skip by default unless refreshing `voice.md`)
If Sudeep wants to tune `voice.md` manually, ask:
1. **"Paste 3–5 personal or external emails/messages you've sent recently that felt like *you at your best*."**
2. **"Paste 1–2 you regret — too defensive, too hasty, too wordy, whatever."**
3. **"Are there any personal phrases, shorthand, or sign-offs you use outside work that we should add to `voice.md`?"**

*(Alternatively, run the **Sent Gmail Corpus Flow** at the bottom of this file.)*

---

## Section 2 — Personal Decision Principles (5 min) → merges into `self/stance.md`
Ask in sequence, drilling on "why" once:
1. **"Think of a recent personal, financial, or career 'no' you gave that you felt great about. What made it a no?"**
2. **"Last time you said 'yes' to a trip, purchase, commitment, or project when you shouldn't have — what was the hidden cost?"**
3. **"When you're evaluating a career opportunity or interview loop, what are your top 3 non-negotiables?"**
4. **"When making a financial or investment call, what's your rule of thumb before committing money?"**

Merge into `self/stance.md` as structured principles (`**<Principle Name>**`, `*Why:*`, `*When it kicks in:*`, `*Counter-example:*`) plus `Heuristics for hard calls`.

---

## Section 3 — Personal Red Lines (3 min) → merges into `self/stance.md`
Ask:
1. **"What family, health, or personal time boundaries are completely non-negotiable for you?"**
2. **"What financial threshold or risk level requires a hard pause and a full `/shyamal-sweep finance` review before saying yes?"**
3. **"In interviews or external negotiations, what is a red flag that makes you walk away immediately?"**

Merge into `self/stance.md` under `Personal Boundaries & Red Lines`.

---

## Section 4 — Recurring Counterparty Archetypes (3 min) → adds `Archetypes` to `self/stance.md`
Ask: **"Name 3–5 types of people/entities you deal with outside day-to-day office work (e.g., 'the pushy recruiter who dodges comp questions', 'the unresponsive travel/service vendor', 'the excited side-project collaborator')."**
For each, capture:
- **Recognize them by**
- **What they want from me**
- **Their typical failure mode**
- **My best-self approach**
- **My worst-self reaction (to avoid)**

---

## Section 5 — Altitude Rules (3 min) → merges into `Altitude Rules` in `self/stance.md`
Ask:
1. **"What kinds of personal, financial, or career asks always deserve a 'wait — should I even do this?' reframe before planning the 'how'?"**
2. **"What kinds of tasks are fine to execute tactically right away without overthinking?"**

---

## Alternate Flow: Refresh `voice.md` from Sent Gmail Corpus (Read-Only)
When Sudeep asks to refresh `self/voice.md` from his sent emails:
1. **Gather corpus (READ-ONLY via `gmail` skill):**
   - Run `gmail messages list --query "in:sent newer_than:365d" --max-results 100` and fetch a representative sample of ~50–100 substantive sent messages across `INNER_CIRCLE`, `COLLABORATOR`, `EXTERNAL_FORMAL`, and `VENDOR_OFFICIAL`.
   - Never send, modify, or delete any email.
   - Redact sensitive account numbers, passwords, or private IDs during analysis.
   - Store temporary scratch analysis only in the conversation's scratch folder and delete it immediately after updating `voice.md`.
2. **Analyze across tiers:** Sentence shape, openers, sign-offs, punctuation habits, pushback phrasing, and grammar-correctness rules.
3. **Update `self/voice.md`** and show Sudeep a summary of what was refined.
