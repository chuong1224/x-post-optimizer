## name: x-post-optimizer
version: 5.2.0
description: >-
Kich hoat khi user upload anh hoac video nhan vat fantasy, dark fantasy, gothic, warrior, angel, demoness va yeu cau viet post X tieng Anh ngan gon de tang reach. BAT CU KHI NAO user noi: viet post X, write X post, tao post cho video nay, optimize X post, ngan gon hon, shorten post, ngan hon nua, refine post, viet caption X, tang reach X, post for this character, toi uu reach. Vi du: user upload anh nhan vat roi goi write X post la skill tu dong phan tich va xuat post chuan 280 ky tu. Skill con xu ly yeu cau ngan gon hon, ngan hon nua de tinh chinh va rut gon post hien tai theo 3 tier rut gon. Khong kich hoat khi user chi hoi kien thuc ve X algorithm, yeu cau viet caption cho mang xa hoi khac (Instagram, TikTok), hoac khong co anh hoac video nhan vat duoc upload kem.

# X Post Optimizer v5.2 — Fantasy Character Edition

**Pattern**: Sequential Workflow
**Skill Type**: Domain-Specific Intelligence
**Body Language**: English (description in Vietnamese no-diacritic per protocol)

## Purpose

Analyze fantasy character images/videos and produce English X posts ≤280 chars with strong
contrast hooks, multi-structure engagement questions, and reach-optimized formatting.
Includes a 3-tier Refinement Mode for shorten requests.

-----

## 1. Mode Detection

|Trigger                                                         |Mode                        |Action                       |
|----------------------------------------------------------------|----------------------------|-----------------------------|
|Image/video uploaded + “write X post” / “viet post X”           |**Generate Mode**           |Run Workflow A (7 steps)     |
|Existing post in context + “shorten” / “ngan gon hon” (1st time)|**Refinement Mode — Tier 1**|Run Workflow B targeting ≤280|
|Same + “ngan hon nua” / “shorter” (2nd time)                    |**Refinement Mode — Tier 2**|Run Workflow B targeting ≤220|
|Same + “shorter still” / “ngan nua” (3rd time)                  |**Refinement Mode — Tier 3**|Run Workflow B targeting ≤150|

Track session state: which post is being refined, current tier, history of cuts.

-----

## 2. Workflow A — Generate Mode (7 mandatory steps)

**Step 1 — Visual analysis**
Extract from image/video: hair color/style, outfit, weapon/power source, dominant color,
background, overall archetype.

**Step 2 — Assign Character Title** (see §5 for fallback hierarchy)

**Step 3 — Write Hook (line 1) — MOST IMPORTANT**
Mandatory structure: `"She doesn't [ordinary action]. She [transformative action]."`
Use Tier S or Tier A patterns from §4. Tier B/C banned.

**Step 4 — Visual description (1–2 lines)**
Only details actually present in the image + Character Title at end.

**Step 5 — Engagement Question** (rotate 6 structures from §6)

**Step 6 — Fixed CTA**
`Drop your answer below — I'm reading every reply 🔥`

**Step 7 — Final Generate Checklist (must pass 100%)**

```
[ ] Total chars ≤ 280 (newline = 1, emoji = 2)
[ ] Hook contrast: Part 2 distinctly stronger (Tier S Action→Essence preferred)
[ ] Hook structure differs from previous post in session
[ ] Character Title not reused in session (or escalated to fallback Tier)
[ ] Question structure differs from previous post (rotate 6 structures)
[ ] Visual description matches actual image — no fabricated details
[ ] No "Kneel" anywhere in post
[ ] Exactly 1–2 emojis at hook start only (none scattered)
[ ] CTA last line is exact wording, not paraphrased
[ ] Tone: dark / regal / mysterious / commanding
```

If any item fails → revise, do NOT output.

-----

## 3. Workflow B — Refinement Mode (7 mandatory steps)

**Step 1 — Detect refinement tier**
Determine current tier from session history (1st request = Tier 1, 2nd = Tier 2, 3rd = Tier 3).
Set character budget: 280 / 220 / 150. Note: Hook (~55) + CTA (~51) + 2 newlines = ~107 char
floor — Tier 3 minimum is constrained by this.

**Step 2 — Lock immutable elements**
Mark these as PROTECTED — must survive every cut:

- Hook contrast structure (only word-level trim allowed, never restructure)
- CTA exact wording (`Drop your answer below — I'm reading every reply 🔥`)
- Character Title (locked at Tier 1–2; may be removed at Tier 3 only)

**Step 3 — Audit current post**
Count current chars. Identify which sections exceed the new budget.

**Step 4 — Apply Cut Priority Order**
Cut sequentially in this order until under budget:

|Order  |Cut Action                  |When                |Notes                                        |
|-------|----------------------------|--------------------|---------------------------------------------|
|**1st**|Trim visual description     |Always start here   |Merge 2 lines → 1, keep 2–3 strongest details|
|**2nd**|Compress engagement question|If still over budget|Drop scenario clause, keep core question     |
|**3rd**|Remove secondary emoji      |If 2 emojis present |Keep 1 emoji at hook start                   |
|**4th**|Drop visual entirely        |Tier 3 only         |Hook + Question + CTA only                   |
|**5th**|Word-trim hook              |LAST RESORT         |Never break contrast structure               |

**Step 5 — Reformat to tier template**

Tier 1 (≤280):

```
[emoji] [Contrast Hook]
[Visual + Title]
[Engagement Question]
Drop your answer below — I'm reading every reply 🔥
```

Tier 2 (≤220):

```
[emoji] [Contrast Hook]
[Visual condensed 1 line + Title]
[Core question]
Drop your answer below — I'm reading every reply 🔥
```

Tier 3 (≤150):

```
[emoji] [Contrast Hook]
[1-line question]
Drop your answer below — I'm reading every reply 🔥
```

**Step 6 — Verify no new content added**
Refinement is subtractive only — no new words, ideas, or details may appear that weren’t
in the previous version. Only cuts and word substitutions for brevity allowed.

**Step 7 — Final Refinement Checklist (must pass 100%)**

```
[ ] Total chars ≤ tier target (280 / 220 / 150 — X-weighted: emoji = 2)
[ ] Hook contrast structure preserved (only word-trim, no rewrite)
[ ] CTA exact wording preserved
[ ] Character Title preserved (Tier 1–2) or dropped intentionally (Tier 3)
[ ] Emoji count: 1–2 (Tier 1) or max 1 (Tier 2–3)
[ ] No new content added — subtractive only
[ ] Cut Priority Order followed (1→5 sequence)
[ ] No "Kneel" still applies
```

If any item fails → revise, do NOT output.

-----

## 4. Contrast Hook Library

### Tier Hierarchy (only Tier S and Tier A allowed)

|Tier |Pattern         |Description                             |
|-----|----------------|----------------------------------------|
|**S**|Action → Essence|Subject’s act IS the thing — STRONGEST  |
|**A**|Passive → Active|Receiver/follower flips to source/leader|

Tiers B/C from previous versions are **deprecated** — they did not reach the contrast
intensity threshold. All hooks must be Tier S or Tier A.

### Tier S — Action → Essence

|Part 1 (does the thing)|Part 2 (IS the thing)|
|-----------------------|---------------------|
|inherits the throne    |IS the throne        |
|carries the weapon     |IS the weapon        |
|plays the music        |IS the music         |
|wields the shadow      |IS the shadow        |
|wears the crown        |IS the crown         |
|summons the storm      |IS the storm         |
|speaks the prayer      |IS the prayer        |
|holds the fire         |IS the fire          |
|paints the void        |IS the void          |
|sings the requiem      |IS the requiem       |
|swings the blade       |IS the blade         |
|pulls the trigger      |IS the verdict       |

### Tier A — Passive → Active

|Part 1 (passive/follower)|Part 2 (active/source)|
|-------------------------|----------------------|
|chases shadows           |casts them            |
|waits for permission     |writes the rules      |
|follows orders           |gives them            |
|breaks hearts            |keeps them            |
|asks                     |takes                 |
|seeks the throne         |becomes the crown     |
|whispers prayers         |answers them          |
|enters the battle        |ends it               |
|begs for mercy           |grants it             |
|falls from heaven        |drags it down with her|
|saves souls              |owns them             |
|fears the void           |becomes it            |

### Mandatory Rules

- Part 2 must be darker / stronger / more transformative than Part 1 in one line
- Prefer Tier S when image dictates; Tier A when action-context preferred
- Banned generic forms: “She is powerful”, “She is the queen”, “She is amazing”
- Never reuse the exact same pair across consecutive posts in a session

-----

## 5. Character Title System (5-Tier Fallback)

For each new character, select from Tier 1 first; escalate when titles repeat.
After ~5 posts of the same archetype, **mandatory** shift to Tier 3+.

|Tier |Pattern               |Examples                                                                      |When to use                 |
|-----|----------------------|------------------------------------------------------------------------------|----------------------------|
|**1**|Archetype + Substance |Void Empress, Flame Seraph, Thorned Seraph, Crimson Onna, Iron Duchess        |Default                     |
|**2**|The + Mythic Role     |The Last Oracle, The Final Verse, The Crown’s Echo, The Black Hymn            |Tier 1 used                 |
|**3**|Negation Names        |She Who Was Forgotten, The Unnamed Heir, The Last Breath, The One Without Name|After 5 same-archetype posts|
|**4**|The + Action Noun     |The Devourer, The Silencer, The Awakened, The Inheritor, The Severance        |Tier 1–3 used               |
|**5**|Composite Mythological|Onna of the Black Tide, Seraph of the Fallen Sun, Empress of the Hollow Crown |Final fallback              |

### Fallback Rules

- Track titles used in current session
- If same archetype appears ≥3 times → mandatory Tier 3+
- If post #N has character similar to post #M → must use different Tier than #M

-----

## 6. Engagement Question Library (6 Structures)

**Never reuse the same structure on consecutive posts.** Rotate through:

|#|Structure        |Template                                     |Example                                                           |
|-|-----------------|---------------------------------------------|------------------------------------------------------------------|
|1|If-then          |“If she [X]… would you [Y]?”                 |If she reached out and asked your true desire… would you tell her?|
|2|What-if inversion|“What if her [X] was [Y]?”                   |What if her silence was the loudest answer you’d ever hear?       |
|3|Direct flip      |“She isn’t [X]. So [Y]?”                     |She isn’t asking. So what will you say anyway?                    |
|4|Inverted choice  |“You won’t [X]. The question is whether [Y].”|You won’t choose her. The question is whether she chooses you.    |
|5|Existential      |“Would you [X]… or [Y]?”                     |Would you remember her name… or would she rewrite yours?          |
|6|Two-path         |“[X] or [Y] — which before [Z]?”             |Bow or burn — which do you pick before she decides for you?       |

### Rotation Rule

- Post #1 uses structure N → Post #2 cannot use N
- After 6 posts, structure N may return but with completely different wording

-----

## 7. Standard Post Structure

```
[emoji] [Contrast Hook]

[Visual description + Character Title]

[Personalized Engagement Question — rotated structure]

Drop your answer below — I'm reading every reply 🔥
```

-----

## 8. Examples

### 8.1 Generate Mode Examples

**Void Empress (Hook Tier A “becomes the crown” + Question Structure 1)**

```
💜 She doesn't seek the throne. She becomes the crown.

Silver hair under the stars, amethyst horns, purple crystal in her palm. The Void Empress.

If she asked your true desire… would you tell the truth?

Drop your answer below — I'm reading every reply 🔥
```

*X-weighted count: 257 / 280*

**Thorned Seraph (Hook Tier S “IS the verdict” + Question Structure 5)**

```
🌹 She doesn't pull the trigger. She IS the verdict.

Black-pink hair flowing, massive black wings, thorny halo glowing. The Thorned Seraph.

Would you survive her aim… or would she rewrite who you ever were?

Drop your answer below — I'm reading every reply 🔥
```

*X-weighted count: ~265 / 280*

**Flame Seraph (Hook Tier S “IS the weapon” + Question Structure 6)**

```
🔥 She doesn't carry the weapon. She IS the weapon.

Blonde ponytail glowing, white-and-gold dress, flaming sword blazing. The Flame Seraph.

Bow or burn — which do you pick before she decides for you?

Drop your answer below — I'm reading every reply 🔥
```

*X-weighted count: ~258 / 280*

### 8.2 Refinement Progression Example (Tier 1 → 2 → 3)

**Original — Tier 1 (≤280)** — *X-count: 257*

```
💜 She doesn't seek the throne. She becomes the crown.

Silver hair under the stars, amethyst horns, purple crystal in her palm. The Void Empress.

If she asked your true desire… would you tell the truth?

Drop your answer below — I'm reading every reply 🔥
```

**User: “ngan gon hon” → Tier 2 (≤220)** — *X-count: 199*
Cuts applied: 1st (visual condensed to 1 short line), 2nd (question reduced to core)

```
💜 She doesn't seek the throne. She becomes the crown.

Silver hair, amethyst horns. The Void Empress has awakened.

Would you tell her the truth?

Drop your answer below — I'm reading every reply 🔥
```

**User: “ngan hon nua” → Tier 3 (≤150)** — *X-count: 138*
Cuts applied: 4th (visual dropped entirely), question already minimal

```
💜 She doesn't seek the throne. She becomes the crown.

Would you tell her the truth?

Drop your answer below — I'm reading every reply 🔥
```

Note: Hook contrast structure and CTA preserved across all three tiers (Step 2 immutables held).

-----

## 9. Gotchas (must read)

1. **280-char limit**: Newline = 1 char, emoji = 2 chars — count precisely.
1. **“Kneel” banned**: Never appears in hook, question, or anywhere.
1. **No hook repetition**: Same contrast structure cannot appear in consecutive posts.
1. **Title tracking**: After 3 posts of same archetype → mandatory Tier 3+ fallback.
1. **Question rotation**: Never reuse structure on consecutive posts.
1. **Visual accuracy**: Only describe details actually in the image — no fabrication.
1. **Tone lock**: Dark / regal / mysterious / commanding. Never cute unless character clearly is.
1. **Emoji count**: 1–2 at hook start only (Tier 1); max 1 in Refinement Tier 2–3.
1. **CTA invariant**: Last line exact wording at every tier — no paraphrase.
1. **Refinement is subtractive**: No new content during shorten — only cuts.
1. **Hook structure protected in Refinement**: Word-trim only, never restructure.
1. **Tier B/C deprecated**: Only Tier S and Tier A hooks accepted in v5.2+.

-----

## 10. Test Cases

**✅ Positive (must trigger)**

- Image upload + “write an X post for this” → Generate Mode
- Video upload + “viet post X cho video nay” → Generate Mode
- Existing post + “ngan gon hon” → Refinement Tier 1
- After Tier 1 + “ngan hon nua” → Refinement Tier 2
- After Tier 2 + “shorter still” → Refinement Tier 3

**❌ Negative (must NOT trigger)**

- “Explain how the X algorithm works” → NO (knowledge query)
- “Write Instagram story caption” → NO (different platform)
- “Optimize my Facebook ad copy” → NO (different platform)

-----

## Version History

|Version|Date      |Changes                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|-------|----------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|v5.2.0 |10/05/2026|Workflow B fully detailed (7 steps + dedicated checklist); Tier B/C hooks deprecated → only Tier S/A allowed; Tier S library expanded (12 pairs incl. upgraded “pulls trigger → IS the verdict”, “swings blade → IS the blade”); language unified to English in body (description stays VN no-diacritic per protocol); added Refinement progression example Tier 1→2→3; Cut Priority Order numbered 1st–5th; tier targets calibrated to X-weighted counting: 280/220/150 (floor of ~107 from Hook+CTA accounted for)|
|v5.1.0 | —         |Step 7 → 10-item checklist; Refinement Mode 3 tiers added; Hook Tier system; Title 5-Tier Fallback; Question Library 6 structures                                                                                                                                                                                                                                                                                                                                                                                   |
|v5.0.0 | —         |Rewrite per Skill Engineer Protocol v2.0; YAML 3-field; description no-diacritic                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|v3.0.0 | —         |Contrast hooks mandatory; “Kneel” removed                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
|v2.0.0 | —         |Structured workflow + templates                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
|v1.0.0 | —         |Initial version                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |