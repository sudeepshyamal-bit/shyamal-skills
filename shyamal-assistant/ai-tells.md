# AI-Tell Cleanup & Two-Pass Editorial Engine (`ai-tells.md`)

Powered by `conorbronsdon/avoid-ai-writing` and anchored in Sudeep's voice (`self/voice.md`). Run this engine at the end of every draft, review, decision, or sweep summary as **subtraction and plain-replacement only**. Sudeep's voice (`self/voice.md`) wins every conflict. Never add artificial drama, contrarianism, staccato fragments, or invented specifics.

---

## 1. Operating Modes & Mandatory Two-Pass Protocol

- **Modes:**
  1. **`Rewrite` (Default on all generated drafts/summaries):** Strips AI-isms using the Tier 1/2/3 tables and 12 structural categories below, then runs **Pass 2**.
  2. **`Detect-Only` (When asked to audit a document):** Lists detected patterns grouped by severity (`P0 Critical` -> `P1 Structural` -> `P2 Lexical/Cluster`) without altering the text.
  3. **`Edit-In-Place` (Used in `review.md` & Refresh Mode):** Makes minimal surgical edits directly in place while preserving Sudeep's structure, quotes, code, and numbers.
- **Why Two Passes Are Mandatory:**
  - **Pass 1 (Lexical & Structural Scrub):** Remove all Tier 1A/1B words, break Tier 2/3 clusters, and fix the 12 structural categories below.
  - **Pass 2 (Rewrite-Artifact Scrub):** Automated Pass 1 edits frequently introduce *secondary* tells (swapping a deleted buzzword for a stiff transition like `"Furthermore,"`, a copula dodge like `"serves as"`, or monotonous sentence lengths). Read the Pass 1 output aloud as the recipient and strip any secondary stiffness before returning.

---

## 2. The 3-Tier Vocabulary Replacement System (`Match Inflected Forms: -ly, -ing, -ed, -s`)

### Tier 1A: AI Frequency Markers (Replace on Sight)
| Flagged AI Word / Phrase | Plain Human Replacement | Flagged AI Word / Phrase | Plain Human Replacement |
| :--- | :--- | :--- | :--- |
| `delve (into)` | dig into, check, look at | `pivotal / crucial / paramount` | key, main, critical, important |
| `tapestry / mosaic / symphony` | mix, setup, details | `foster / cultivate` | build, grow, support |
| `landscape / realm / sphere` | space, market, area | `synergy / interplay` | fit, connection, how X & Y work |
| `paradigm` | model, approach | `elevate / uplift / amplify` | improve, raise, strengthen |
| `beacon / cornerstone / bedrock / linchpin` | guide, core part, key factor | `unleash / unlock / harness` | open up, use |
| `testament to` | proof of, shows | `seamless(ly)` | smooth(ly), direct |
| `underscores / showcases` | shows, proves | `robust / battle-tested` | solid, strong, reliable |
| `embark (on)` | start, begin | `navigate` (figurative) | handle, work through |
| `meticulous(ly) / intricate / multifaceted / nuanced` | *(state the specific detail)* | `overarching / poised / profound / spearhead / transformative / unprecedented / vibrant / game-changer` | *(cut or replace with plain fact/verb)* |

### Tier 1B: Clarity & Copula-Avoidance Edits (Replace Inflated Formality)
| Inflated Form | Plain Human Replacement | Inflated Form | Plain Human Replacement |
| :--- | :--- | :--- | :--- |
| `utilize / leverage` | use | `serves as / stands as / acts as / represents / functions as` | **is / are** *(never dodge plain copulas)* |
| `in order to` | to | `features / boasts / sports / encompasses` | **has / includes** |
| `due to the fact that / owing to` | because | `commence / initiate` | start |
| `facilitate` | help, run, unblock | `prior to` / `subsequent to` | before / after |
| `at this point in time / currently` | now | `in the event that` / `with regard to` | if / on, about |

### Tier 2: Cluster-Only Flags (Fine Once; Strip When $\ge 2$ Appear in the Same Paragraph)
- **Verbs & Adjectives:** `align`, `ensure`, `enhance`, `optimize`, `streamline`, `comprehensive`, `dynamic`, `innovative`, `strategic`, `significant`, `vital`, `holistic`, `actionable`, `impactful`.
- **Conjunctive Adverbs:** `notably`, `furthermore`, `moreover`, `consequently`, `nevertheless`, `nonetheless`, `additionally`, `importantly`.
- **Hedge Stacks:** Never allow $\ge 2$ of `might`, `perhaps`, `potentially`, `possibly`, `I think`, `just` in one sentence.

### Tier 3: Density & Multi-Word Boilerplate Flags (Strip When Repeating $\ge 3\%$ or When $\ge 3$ Stack)
- `"the integration of"`, `"in today's fast-paced..."`, `"a wide range of"`, `"plays a key role in"`, `"it is worth noting that"`, `"at the end of the day"`, `"needless to say"`, `"it goes without saying"`.

---

## 3. All 12 Structural, Rhythm & Conversational-Register Categories

1. **Em Dashes (`P0`):** **Zero em dashes (`—` or ` -- `) anywhere** in prose, tables, headings, or summaries. Use a comma, colon, parentheses, or period.
2. **Sycophantic & Chatbot Artifacts (`P0`):** Strip `"Certainly!"`, `"Great question"`, `"I hope this helps"`, `"Feel free to"`, `"Let me know if you need anything else"`, `"I'm thrilled/excited to share"`.
3. **Meta-Narration & Throat-Clearing (`P0`):** Strip `"In this email/document, I will..."`, `"Let's dive in"`, `"Here's the thing"`, `"Let that sink in"`, `"I wanted to reach out"`, `"I hope this email finds you well"`.
4. **Copula Avoidance (`P1`):** Never swap simple linking verbs (`is`, `are`, `has`) for press-release verbs (`serves as`, `stands as`, `boasts`, `features`).
5. **Superficial `-ing` Participle Tails (`P1`):** Strip participial clauses tacked onto the end of a sentence to fake analytical depth (`"..., highlighting our commitment"`, `"..., ensuring a smooth process"`, `"..., underscoring the importance of"`, `"..., reflecting a broader trend"`). State the hard fact or cut the tail.
6. **Negative Parallelisms & Mirrored Contrasts (`P1`):** Strip `"It's not just X, it's Y"`, `"less about X, more about Y"`, `"not merely X, but Y"`. *(Protected exception: Sudeep's specific strategic framing `"my biggest concern is not X, but Y"` when naming a real risk).*
7. **Compulsive Rule of Three (`P1`):** LLMs compulsively group adjectives (`"clear, concise, and actionable"`), verbs (`"plan, execute, and scale"`), or examples into neat triads. Break ornamental triads unless there are genuinely 3 distinct factual items.
8. **False Ranges (`P1`):** Strip synthetic `"from X to Y"` spectrums where X and Y do not form a real measurable range.
9. **Formulaic Concessive Openers (`P1`):** Do not open replies or paragraphs with predictable `"While X is impressive, Y..."` or `"Despite X, Y remains..."` structures. Start with the point.
10. **Sentence & Paragraph-Length Uniformity (`P2`):** Avoid monotonous blocks where every paragraph or bullet has the exact same 2-sentence / 20-word cadence. Vary sentence length naturally.
11. **Paragraph-Reshuffle Immunity & Bare-Noun Bullets (`P2`):** If two paragraphs can swap places without breaking the flow, cut or sequence them. Every bullet must contain a concrete fact, verb, owner, or date, never a bare abstract noun phrase.
12. **Conversational Wall-of-Text (`P1` for WhatsApp/Chat):** Never output a reply under 150 words as 4+ unbroken sentences with no line breaks, and never use email headers, formal numbered lists, or sign-off names on WhatsApp/DM.

---

## 4. Protected Contract: Never Edit These (They Are Sudeep's Voice)
- `"Let's <verb>"`, `"Quick FYI:"`, `"Got it"`, `"Okay, got it"`, `"Sure"`, `"Thanks"`, `"Awesome, thanks"`, `"give me 2 mins"`, `"Keep me posted"`, `"Will keep you posted!!"`, `"Family first!!"`.
- `!!` after warm or reassuring notes in personal/collaborator tiers, and `"And really sorry this long message!!"` in genuinely long strategic notes.
- `:)` / `🙂` / `:slightly_smiling_face:` and celebration emojis (`🎂`, `🎉`).
- **The capital letter after the opener comma** (`"Hey <Name>, I got..."`, `"Hi <Name>, Good morning!"`).
- **Bold-topic labels** in sweep trackers and plans (`"**Flight Bookings:** ..."`).
- Verbatim quotes, code blocks, account numbers, UTRs/PNRs, URLs, and YAML frontmatter.
