# Local Pack Lab — Design System

## Overview

**Local Pack Lab (LPL)** is a local SEO education and tools brand targeting exterior service contractors (pressure washers, roofers, painters, landscapers, etc.). The brand teaches Google Business Profile (GBP) optimization and local search ranking through social carousels, guides, and checklists.

**Sources used to build this design system:**
- `LPL Carousel.html` — Instagram carousel prototype (1080×1350px, 5-slide format)

---

## CONTENT FUNDAMENTALS

### Voice & Tone
- **Direct and practitioner-first.** Speaks to the business owner doing the work, not a marketing manager.
- **Second person ("you", "your").** Always addresses the reader directly.
- **Short, punchy sentences.** No fluff. Every word earns its place.
- **Data-backed confidence.** Uses specific stats and percentages to establish authority (e.g. "23% profile completeness").
- **No emoji.** Brand does not use emoji in content or UI.
- **No exclamation points** in headlines. Confidence doesn't need to shout.

### Casing
- **Headlines:** Title Case or Sentence case — both used; sentence case preferred for longer headlines.
- **Labels/eyebrows:** ALL CAPS with wide letter-spacing (monospace, 0.18–0.22em tracking).
- **CTAs:** ALL CAPS, tight letter-spacing (0.04em).
- **Body copy:** Sentence case only.

### Copy Examples
> "Why Your Pressure Washing Business Doesn't Show Up on Google Maps"
> "Proximity alone won't save a weak profile"
> "5 fixes you can do this weekend"
> "Link in bio → Local Pack Lab GBP Guide"

### Content Structure (Carousel)
1. **Hook** — Bold problem statement headline + eyebrow label + subhead tease
2. **Problem** — Data/context with stat boxes and a pullquote
3–4. **Fixes** — Numbered list items with headline + descriptor
5. **CTA** — Outcome promise + single clear action

---

## VISUAL FOUNDATIONS

### Color System
Four palette options, all dark-background. Default is **Midnight Lime**.

| Token | Midnight Lime | Navy Electric | Charcoal Ember | Deep Plum |
|---|---|---|---|---|
| `--bg` | `#0e1016` | `#060c24` | `#13100c` | `#100d1a` |
| `--fg` | `#f0f0ee` | `#eef2ff` | `#f5f0ea` | `#f2eeff` |
| `--accent` | `#c8f135` | `#4d9fff` | `#ff6b2b` | `#b57bff` |
| `--accent-bg` | `rgba(accent, 0.06)` | same | same | same |
| `--accent-dim` | `rgba(accent, 0.2)` | same | same | same |
| `--accent-ghost` | `rgba(accent, 0.04)` | same | same | same |

**Color rules:**
- Backgrounds are near-black, slightly warm/cool tinted — never pure `#000000`
- Foreground is warm-off-white — never pure `#ffffff`
- Single accent per palette; accent used for: highlights, labels, CTAs, borders, stats
- Body text uses `rgba(fg, 0.55)` opacity — never a separate gray token
- Borders use `rgba(255,255,255,0.08)` — universal subtle divider
- Ghost backgrounds use `rgba(accent, 0.04–0.07)`

### Typography
**Two fonts only:**
- `Space Grotesk` (sans-serif) — all body, headlines, UI text
- `Space Mono` (monospace) — all labels, eyebrows, counters, wordmark, metadata

**Type Scale (base = 1.0; adjustable via `--scale`):**
| Role | Size | Weight | Notes |
|---|---|---|---|
| Hero headline | `90px × --scale` | 700 | `letter-spacing: -0.025em`, `line-height: 1.0` |
| CTA headline | `86px × --scale` | 700 | `letter-spacing: -0.03em` |
| Fix headline | `36px × --scale` | 700 | `letter-spacing: -0.01em` |
| Body large | `32px × --scale` | 500 | `line-height: 1.5` |
| Pullquote | `26px × --scale` | 600 | italic |
| Body small | `24px × --scale` | 400/500 | `line-height: 1.6` |
| Fix descriptor | `20px × --scale` | 400 | `line-height: 1.5` |
| Section label | `12px` | 700 | Mono, `letter-spacing: 0.22em`, ALL CAPS, accent color |
| Wordmark | `13px` | 700 | Mono, `letter-spacing: 0.18em`, ALL CAPS |
| Counter/meta | `11–13px` | 400/700 | Mono, `rgba(fg, 0.2–0.35)` |

### Spacing & Layout
- Base slide padding: `72px 80px` (top/bottom / left/right)
- Section gaps: `32–80px` (large gaps between major sections)
- Item gaps: `12–20px` (within components)
- Fix item padding: `44px 0` with `1px solid rgba(255,255,255,0.08)` dividers

### Surfaces & Backgrounds
- **Primary:** near-black `--bg`, no gradient, flat fill
- **Texture overlays (optional):** dot grid (`radial-gradient`, 36px repeat) or horizontal lines (48px repeat) at `rgba(255,255,255,0.02–0.13)` opacity
- **Card/box backgrounds:** `rgba(255,255,255,0.04)` with `1px solid rgba(255,255,255,0.08)` border
- **Accent ghost panels:** `rgba(accent, 0.06)` background — used for pullquotes and continue-hint blocks
- **No gradients** on backgrounds. Gradients only used via CSS pseudo-elements for texture.
- **Decorative oversized type:** Large ghosted characters (`--accent-ghost`) behind slide content — purely decorative, `z-index: 0`, `user-select: none`
- **Decorative circles:** Concentric rings using `border: 1px–2px solid var(--accent-dim)` at low opacity — used on CTA slides

### Corner Radius
Three modes via `--radius`:
- `Sharp`: `4px`
- `Soft`: `12px`
- `Round`: `24px`
Default: `4px` (Sharp). Pills and tags use `--radius`; pullquote uses `0 var(--radius) var(--radius) 0`.

### Animation & Interaction
- No animations defined in the carousel system (static slides).
- Hover states not yet defined — to be established in interactive surfaces.

### Borders & Dividers
- Component borders: `1px solid rgba(255,255,255,0.08)`
- Accent left-border (pullquote): `4px solid var(--accent)`
- Dashed outline (continue-hint): `1px dashed var(--accent-dim)`
- No drop shadows used — elevation is implied by background contrast alone.

### Imagery
- No photography used in existing carousel. Imagery is replaced by:
  - Oversized ghosted typographic elements
  - Decorative geometric shapes (concentric circles)
  - Dot/line texture overlays
  - Stat data visualized as number+label boxes

### Iconography
- **No icon library** currently used.
- Unicode arrows used as directional cues: `→`, `↗`
- No emoji.
- No SVG icons.
- Recommend: if icons are added, use a stroke-weight-consistent set (e.g. Lucide) at 1.5px stroke, matching the monospace/grid precision of the type system.

---

## FILE INDEX

```
README.md                     ← This file
SKILL.md                      ← Agent skill definition
colors_and_type.css           ← All CSS custom properties
preview/
  colors-palettes.html        ← Color palette swatches
  colors-semantic.html        ← Semantic color tokens in use
  type-scale.html             ← Full type scale specimen
  type-roles.html             ← Type roles (wordmark, label, counter, etc.)
  spacing-tokens.html         ← Spacing + radius + border tokens
  surfaces.html               ← Background surfaces + textures
  component-pills.html        ← Algo pills (active/dim states)
  component-pullquote.html    ← Pullquote block
  component-statbox.html      ← Stat box
  component-fixitem.html      ← Fix/list item
  component-cta.html          ← CTA block
  component-wordmark.html     ← Wordmark + counter
ui_kits/
  social-carousel/
    README.md
    index.html                ← Full carousel UI kit
```
