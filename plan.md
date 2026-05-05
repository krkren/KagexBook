# KAGEX Book — Translation Consistency Issues

*Last reviewed: 2026-05-05*

---

## 1. Script Comment Verb Tense Inconsistency (highest priority)

Script table comments (`class="KAGEXスクリプト"`) use **four different verb forms** throughout the book. They should follow a single convention — preferably simple present/imperative to describe what each command does:

| Current pattern | Examples |
|---|---|
| **Past tense / abbreviated** | "Background displayed.", "Cleared character sprite.", "Changed location." |
| **Present continuous** | "Rotating character sprite 180 degrees counter-clockwise.", "Changing background xpos and ypos values over 2 seconds." |
| **Simple present (imperative)** | "Display the background.", "Play BGM.", "Halve the sound effect volume." |
| **Passive present perfect** | "The sound effect has been played synchronously.", "The sound effect has been faded out synchronously." |
| **Present simple declarative** | "The background is displayed.", "The screen is shaking.", "Sound effect is playing." |
| **Colloquial / filler** | "Shake shake shake." |

### Recommended convention
Use **simple present, active voice** — describe what the command *does*:

- ❌ "Background displayed." → ✅ "Displays the background."
- ❌ "Rotating character sprite 180 degrees counter-clockwise." → ✅ "Rotates character sprite 180° counter-clockwise."
- ❌ "The sound effect has been played synchronously." → ✅ "Plays the sound effect synchronously."

---

## 2. Inconsistent Script Comment Styles (within same category)

Even within the "past tense abbreviated" group, phrasing is inconsistent:

- "Background displayed." vs "Character sprite displayed." — should unify article usage
- "Changed location to Town and time to Day." vs "Changed location." — one specifies details, the other is terse. Decide: always concise, or always fully descriptive?
- "The background and portrait are displayed." (present) vs "Background displayed." (past) — same pattern, different tense

---

## 3. Character Name ("Portrait" vs "Character Sprite")

In the **prose**, the term is consistently "**character sprite**" (~90 uses). But in **script table comments**, it's alternately called "**portrait**" (~47 uses):

- Prose: *"Next, we'll display **character sprites** after the background."*
- Script comment: *"The **portrait** is displayed." / "Slant the **portrait** -100 horizontally."*

Both refer to the same thing (the `char` tag / Tachie). Pick one term and use it everywhere. Recommendation: stick with "**character sprite**" throughout for clarity, or add "(portrait)" on first mention if the Japanese term is preferred.

---

## 4. Quotation-Mark Inconsistency in Character Dialogue (Script Comments)

Japanese 「」and English "" quotes are both used for character dialogue lines inside script examples:

- Japanese brackets: `【Shiori】「Display the character sprite.」` *(26 occurrences)*
- English quotes: `【Shiori】"Hello."` *(76 occurrences)*

Choose one standard. Since the book is in English, recommend **English "double quotes"** for all dialogue and remove 「」from script comment text content. (Note: Some Japanese 「」appear inside what should be English dialogue — these look like artifacts of auto-conversion during translation.)

---

## 5. Repetitive / Conversational Digressions

Several paragraphs contain author's personal musings that could be tightened for a reference manual:

- **Chapter 3, "Pixels" section**: The entire paragraph about 2ch/eroge wide-screening ("(Reference: 2ch …)") is a long digression with a link to an adult-game forum. Consider trimming or removing the URL citation.
- **Chapter 3, "Pixels"** continued: *"A girl displayed on a vertical screen is 30% cuter just because of that."* — this informal tone stands out against the technical reference style.
- **Chapter 1, Introduction**: *"This was truly useless chatter."* — acknowledges its own digressiveness. Acceptable for an informal book but worth noting.

---

## 6. "The background and portraits are displayed." — Pluralization Inconsistency

Some script comments use singular ("portrait") and others plural ("portraits"):

- *"The background and portrait are displayed."*
- *"The background and portraits are displayed."*

If only one character sprite is on screen, the comment should say "portrait" (singular). If multiple, "portraits" (plural). The script comments don't always match the actual number of sprites being displayed.

---

## 7. "Event CG" vs "CG" Inconsistency

Throughout the prose and comments, event CGs are called:

- "**event CG**" — most common (~40 uses)
- "**CG**" alone (ambiguous — could mean any computer graphic)
- "**one-page pictures/CG/stills**" — parenthetical explanation in one location

Recommendation: always use "**event CG**" when referring to the KAGEX concept; use "CG" only when clearly referring to a game asset.

---

## 8. Minor Wording Issues (Grammar / Clarity)

| Location | Current Text | Suggested Fix |
|---|---|---|
| Ch 1, Intro | *"It's too complex for those without programming experience."* | *"TJS is more complex for those without programming experience."* — "too complex" is vague (too complex for what?) |
| Ch 2, File Extensions | *"if you don't understand with text alone"* | *"if the text-only instructions aren't clear enough"* — awkward phrasing |
| Ch 3, Image Positioning | *"You can shift it to the right by the specified value. You can also shift it to the left by specifying a negative value."* | Consider reversing order for clarity: first explain positive → right, then negative → left, or merge into one sentence. |
| Ch 5, Sound Effects | *"Sound effects work exactly the same way, just using SE Volume instead of BGM Volume."* | Verify: "SE Volume" is intentional (menu option). Otherwise should read "using sound effect volume instead of BGM volume." |
| Ch 7, Appendix | *"The name doesn't really matter"* | Consider more formal: *"the exact terminology isn't critical"* |

---

## Summary by Priority

| Priority | Issue | Scope |
|---|---|---|
| **P0** (fix first) | Script comment tense inconsistency | ~122 script comments |
| **P0** | Portrait vs character sprite naming | ~47 occurrences |
| **P1** | 「」 vs "" dialogue quotes | ~26 Japanese-bracket lines |
| **P1** | Singular vs plural "portrait/portraits" | Scattered in scripts |
| **P2** | Event CG vs CG ambiguity | ~8 locations |
| **P3** | Conversational digressions tone | 3–5 paragraphs |
| **P3** | Minor grammar/phrasing fixes | 5 isolated lines |

---

*Note: The class-name standardization (章タイトル, 節タイトル, KAGEXスクリプト表), SE → "sound effect", and visual layout changes have already been completed.*
