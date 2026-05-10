# x-post-optimizer

[![Version](https://img.shields.io/badge/version-5.2.0-blueviolet)](https://github.com/chuong1224/x-post-optimizer)
[![License](https://img.shields.io/badge/license-MIT-green)](https://github.com/chuong1224/x-post-optimizer/blob/main/LICENSE)
[![Grok Skill](https://img.shields.io/badge/Grok-Custom_Skill-9B59B6)](https://github.com/chuong1224/x-post-optimizer)
[![Last Commit](https://img.shields.io/github/last-commit/chuong1224/x-post-optimizer)](https://github.com/chuong1224/x-post-optimizer/commits/main)
[![GitHub Repo stars](https://img.shields.io/github/stars/chuong1224/x-post-optimizer?style=social)](https://github.com/chuong1224/x-post-optimizer/stargazers)

**Grok Skill v5.2.0** — Fantasy Character Edition. Analyze uploaded fantasy/dark fantasy/gothic/warrior/angel/demoness images or videos and generate optimized English X posts (≤280 chars) with powerful contrast hooks, rotated engagement questions, and a unique 3-tier progressive refinement mode for shortening requests.

---

## English

### Overview

This skill activates on image/video upload + commands like “viet post X”, “write X post”, “optimize X post”, or “ngan gon hon” / “shorter” for existing posts. It performs deep visual analysis, assigns fitting Character Titles via 5-tier fallback, builds Tier S or Tier A contrast hooks (deprecated older tiers), rotates through 6 engagement question structures, and enforces strict checklists before output. Includes full 3-tier Refinement Mode that progressively shortens while protecting hook structure, CTA, and key elements.

**Trigger phrases:** “viet post X”, “write X post”, “tao post cho video nay”, “optimize X post”, “ngan gon hon”, “ngan hon nua”, “shorter still”, “post for this character”, “toi uu reach”.

**Not triggered** for pure X algorithm questions, other platforms (Instagram/TikTok/Facebook), or when no visual upload is provided.

### Key Features

- **Workflow A (Generate)**: 7 mandatory steps including visual analysis, character title assignment, Tier S/A hook construction, visual description, rotated question, fixed CTA, and 10-item checklist.
- **Workflow B (Refinement)**: 7-step process with tier detection (1→3), immutable element locking (hook structure, CTA, title), cut priority order, and dedicated checklist. Targets: ≤280 / ≤220 / ≤150 chars.
- **Contrast Hooks**: Only Tier S (Action → Essence) and Tier A (Passive → Active) allowed — 24 powerful pairs. No generic or weak hooks.
- **Character Title System**: 5-tier fallback with session tracking to avoid repetition; escalates after repeats.
- **Engagement Questions**: 6 rotating structures (If-then, What-if, Direct flip, etc.) — never consecutive reuse.
- **Strict Guardrails**: 280-char X-weighted counting, no “Kneel”, visual accuracy only, tone lock (dark/regal/mysterious/commanding), emoji discipline, CTA invariance.
- **Session Awareness**: Tracks used titles, hooks, and question structures to ensure variety.

### Standard Output Structure

```
[emoji] [Contrast Hook]

[Visual description + Character Title]

[Personalized Engagement Question]

Drop your answer below — I'm reading every reply 🔥
```

### Refinement Mode (Progressive Shortening)

- **Tier 1** (“ngan gon hon”): Full structure, condensed visual.
- **Tier 2** (“ngan hon nua”): 1-line visual, core question.
- **Tier 3** (“shorter still”): Hook + minimal question + CTA only (visual dropped).

Hook contrast and CTA are **protected** across all tiers.

### Examples

See `SKILL.md` for complete Generate Mode examples (Void Empress, Thorned Seraph, Flame Seraph) and the full Tier 1→2→3 refinement progression with exact cuts applied.

### Gotchas & Best Practices

- Count precisely: newline=1, emoji=2.
- Only describe what is visibly in the image/video.
- Rotate hooks and question structures every post.
- After 3+ same archetype → force higher title tier.
- Refinement is strictly subtractive — no new ideas.
- Output **only** raw post text.

---

## Tiếng Việt

### Tổng quan

Skill được kích hoạt khi user upload ảnh/video nhân vật fantasy (dark fantasy, gothic, warrior, angel, demoness) và yêu cầu viết post X tiếng Anh ngắn gọn tối ưu reach, hoặc “ngan gon hon” / “ngan hon nua” để rút gọn post hiện tại. Skill thực hiện phân tích visual sâu, gắn Character Title theo hệ thống 5 tier, xây dựng hook Tier S/A mạnh mẽ, xoay vòng 6 cấu trúc câu hỏi tương tác, và áp dụng checklist nghiêm ngặt. Hỗ trợ đầy đủ 3-tier Refinement Mode với mục tiêu 280/220/150 ký tự.

**Cụm từ kích hoạt:** “viet post X”, “write X post”, “tao post cho video nay”, “optimize X post”, “ngan gon hon”, “ngan hon nua”, “shorter still”, “post for this character”, “toi uu reach”.

**Không kích hoạt** với câu hỏi thần thấu X algorithm, caption cho nền tảng khác, hoặc không có upload ảnh/video.

### Tính năng nổi bật

- **Workflow A (Generate)**: 7 bước bắt buộc — visual analysis, title, hook Tier S/A, mô tả, câu hỏi xoay vòng, CTA cố định, checklist 10 mục.
- **Workflow B (Refinement)**: 7 bước, phát hiện tier tự động, bảo vệ cấu trúc hook/CTA/title, thứ tự cắt thông minh, checklist riêng. Mục tiêu: ≤280 / ≤220 / ≤150 ký tự.
- **Hook đội chiếu**: Chỉ cho phép Tier S (Action → Essence) và Tier A (Passive → Active) — 24 cặp mạnh. Loại bỏ các tier yếu cũ.
- **Hệ thống Character Title**: 5 tier fallback + tracking session để tránh lặp, tự động nâng cao sau 3–5 lần lặp archetype.
- **Câu hỏi tương tác**: 6 cấu trúc xoay vòng (If-then, What-if, Direct flip, Inverted choice, Existential, Two-path).
- **Rào cản nghiêm ngặt**: đếm ký tự X-weighted, cấm “Kneel”, chỉ mô tả chi tiết thật có trong ảnh, tone dark/regal/mysterious/commanding, emoji 1–2 cái ở đầu hook, CTA bắt biến.

### Cấu trúc post chuẩn

```
[emoji] [Contrast Hook]

[Visual description + Character Title]

[Personalized Engagement Question]

Drop your answer below — I'm reading every reply 🔥
```

### Chế độ Rút gọn (3 Tier)

- **Tier 1** (“ngan gon hon”): Đầy đủ cấu trúc, visual ngắn hơn.
- **Tier 2** (“ngan hon nua”): Visual 1 dòng, câu hỏi cốt lõi.
- **Tier 3** (“shorter still”): Chỉ Hook + câu hỏi tối thiểu + CTA (bỏ visual).

Cấu trúc hook và CTA được **bảo vệ** qua tất cả các tier.

### Ví dụ

Xem `SKILL.md` để có đầy đủ ví dụ Generate Mode (Void Empress, Thorned Seraph, Flame Seraph) và tiến trình rút gọn Tier 1 → 2 → 3 với chi tiết các lược cắt.

### Lưu ý quan trọng

- Đếm chính xác: newline = 1, emoji = 2.
- Chỉ mô tả được thấy trong ảnh/video.
- Xoay hook và cấu trúc câu hỏi mỗi post.
- Sau 3+ archetype giống nhau → bắt buộc dùng title tier cao hơn.
- Refinement chỉ được cắt bớt — không thêm ý tưởng mới.
- Output **chỉ** raw post text, không meta hay giải thích.

---

## Version History

| Version | Date       | Changes                                      |
|---------|------------|----------------------------------------------|
| 5.2.0   | 2026-05-10 | Workflow B fully detailed (7 steps + checklist); Tier B/C hooks deprecated → only Tier S/A; Tier S library expanded (12 pairs); added full 3-tier refinement progression example; Cut Priority Order; tier targets calibrated to X-weighted (280/220/150); language unified in body |
| 5.1.0   | —         | Step 7 → 10-item checklist; Refinement Mode 3 tiers; Hook Tier system; Title 5-Tier Fallback; Question Library 6 structures |
| 5.0.0   | —         | Rewrite per Skill Engineer Protocol v2.0; YAML 3-field; description no-diacritic |
| 3.0.0   | —         | Contrast hooks mandatory; “Kneel” removed |
| 2.0.0   | 2026-05-08 | Structured workflow + templates, bilingual README |
| 1.0.0   | —         | Initial version |

---

*Skill version: 5.2.0*  |  Repo: https://github.com/chuong1224/x-post-optimizer  |  Licensed under [MIT](LICENSE)

Tạo bởi N0v4Ph4n cho Grok users