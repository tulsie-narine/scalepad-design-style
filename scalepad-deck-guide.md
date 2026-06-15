# ScalePad PowerPoint Deck Guide

> Extracted live from scalepad.com — June 2026  
> Companion to `scalepad-design-system.md`. Purpose-built for slide deck production.

---

## Quick-start checklist

Before building any ScalePad deck, confirm:

- [ ] Theme: **dark** (sales, launch, partner) or **light** (board, internal, data-heavy)
- [ ] Primary product accent (see token table below)
- [ ] Slide count: 8–14 sales pitch · 10–18 all-hands · 6–10 launch/announcement
- [ ] Font Inter embedded in the `.pptx` file (not just referenced)
- [ ] Logo variant matches theme (dark wordmark on light, white wordmark on dark)

---

## Logo & Asset URLs

All assets are served as SVGs directly from scalepad.com. Link or download for offline use.

### ScalePad master logo

| Variant | URL |
|---------|-----|
| Default (dark wordmark) | `https://www.scalepad.com/scalepad-logo.svg` |
| White (for dark backgrounds) | Use CSS filter: `brightness(0) invert(1)` on the default SVG |

**Lockup:** `·· ScalePad` — the dotted grid mark followed by the wordmark. Never separate the mark from the wordmark, never recolor either element independently.

**Clearspace:** minimum equal to the cap-height of the "S" on all four sides.

**Placement on slides:** bottom-left corner at 0.25" margin, or top-left on cover slides. Never centered unless it's a standalone logo-wall or closing slide.

### Product logos (horizontal lockup)

| Product | Color lockup | White lockup |
|---------|-------------|--------------|
| Lifecycle Manager | `https://www.scalepad.com/product-logos/lifecycle-manager.svg` | `https://www.scalepad.com/product-logos/lifecycle-manager-white.svg` |
| ControlMap | `https://www.scalepad.com/product-logos/controlmap.svg` | `https://www.scalepad.com/product-logos/controlmap-white.svg` |
| Quoter | `https://www.scalepad.com/product-logos/quoter.svg` | `https://www.scalepad.com/product-logos/quoter-white.svg` |
| Backup Radar | `https://www.scalepad.com/product-logos/backup-radar.svg` | `https://www.scalepad.com/product-logos/backup-radar-white.svg` |
| Cognition360 | `https://www.scalepad.com/product-logos/cognition360.svg` | `https://www.scalepad.com/product-logos/cognition360-white.svg` |

### Product icons (square app icons, for suite overviews)

| Product | URL |
|---------|-----|
| Lifecycle Manager | `https://www.scalepad.com/product-icons/lifecycle-manager.svg` |
| ControlMap | `https://www.scalepad.com/product-icons/controlmap.svg` |
| Quoter | `https://www.scalepad.com/product-icons/quoter.svg` |
| Backup Radar | `https://www.scalepad.com/product-icons/backup-radar.svg` |
| Cognition360 | `https://www.scalepad.com/product-icons/cognition360.svg` |

### Compliance badges

| Badge | URL |
|-------|-----|
| SOC 2 Type II | `https://www.scalepad.com/compliance/soc-2-type-ii.svg` |
| ISO 27001 | `https://www.scalepad.com/compliance/iso-27001.svg` |

---

## Product Color Tokens

Pulled directly from `:root` CSS on scalepad.com. Use these as the canonical accent per product.

| Product | CSS Token | Hex | Usage |
|---------|-----------|-----|-------|
| Lifecycle Manager | `--color-product-lm` | `#4ba384` | Teal-green |
| Lifecycle Insights | `--color-product-lci` | `#007674` | Deep teal |
| ControlMap | `--color-product-cm` | `#693568` | Deep purple |
| Quoter | `--color-product-qt` | `#b71e74` | Magenta-pink |
| Backup Radar | `--color-product-br` | `#216092` | Deep blue |
| Cognition360 | `--color-product-c360` | `#cf304c` | Deep red |
| Platform accent | `--color-platform-accent` | `#8f96ff` | Indigo (platform/API slides) |

### Mapping to scalepad-deck skill tokens

| Deck skill token | Product | Hex |
|-----------------|---------|-----|
| `ATMOSPHERE` | Lifecycle Manager | `#4ba384` |
| `GALAXY` | ControlMap | `#693568` |
| `COSMOS` | Quoter | `#b71e74` |
| `RADAR` | Backup Radar | `#216092` |
| `NEBULA` | Cognition360 | `#cf304c` |

---

## Product Hero Gradients

Each product page uses a full-bleed dark gradient hero. These are the exact values for slide cover backgrounds.

| Product | Hero gradient | Direction |
|---------|--------------|-----------|
| **Lifecycle Manager** | `#022620` → `#1a4f40` → `#4ba384` | 45deg |
| **ControlMap** | `#24122d` → `#693568` → `#9e579e` | 45deg |
| **Quoter** | `#3d0e2d` → `#a0295a` → `#e0608e` | 45deg (computed: `#6d2536` → `#b92e47` → `#fe7780`) |
| **Backup Radar** | `#0b1e38` → `#1a4a7a` → `#4a8fc4` | 45deg |
| **Cognition360** | `#6d2536` → `#b92e47` → `#fe7780` | 45deg |
| **ScalePad (suite)** | `#0d1f30` → `#42436c` | 135deg radial overlay |

### Overlay layer (all product heroes)

Every product hero adds a radial overlay on top of the base gradient:

```
radial-gradient(circle at 88% 8%, rgba(255,255,255,0.13), transparent 34%),
linear-gradient(45deg, rgba(0,0,0,0.26), transparent 70%)
```

Apply this on top of any product hero gradient for the authentic ScalePad look.

### Light hero gradient (About / general pages)

Used when a light-mode hero wash is needed (e.g., internal decks, agenda slides):

```
radial-gradient soft wash: teal-green (#9FE1CB) top-left → pink-purple (#E8B4C8) top-right
```

---

## Slide Layout Patterns

Seven repeating layout patterns observed across the site. Map these directly to PPTX slide types.

### 1. Full-bleed dark hero (Cover / Section divider)

- **Canvas:** product gradient (full bleed, edge to edge)
- **Logo:** white product logo centered, ~200px wide
- **Headline:** white, Inter 800, 48–60pt, centered, max 2 lines
- **Emphasis word:** Gold shimmer gradient inline — `#fbe49f → #ffca05 → #f5aa1b`
- **Subhead:** white/70%, Inter 400, 18–22pt, centered, max 2 lines
- **CTAs:** Gold primary button + white-outline secondary button, centered
- **Watermark:** large faded product icon at ~30% opacity bottom-right
- **Use for:** cover slide, product section dividers

### 2. Two-column: text left / visual right

- **Left (45%):** eyebrow label (Gold, 11px, caps, 0.1em spacing) → H2 (dark, 800, 32–38pt) → body text (muted, 400, 16–18pt) → optional text CTA
- **Right (55%):** product screenshot in white card with subtle shadow, or illustration
- **Background:** `#f5f7f9` canvas (light theme) or `#0a1c2b` navy (dark theme)
- **Use for:** feature explanation, problem/solution, key capability

### 3. Stat hero (single metric)

- **Layout:** full-width centered
- **Eyebrow:** Gold caps label above
- **Stat:** Inter 800, 80–120pt, Dark Matter or white
- **Label:** Inter 500, 14pt, uppercase, muted, below stat
- **Accent:** Gold underline or Gold color on the stat number
- **Use for:** impact moments — "74K+ QBR hours saved"

### 4. Stat grid (3-up or 4-up)

- **Grid:** 3 or 4 equal columns, divided by hairline borders
- **Each cell:** large number (Inter 800, 48–64pt) + uppercase label (12pt, 500, muted, 0.08em spacing)
- **Background:** white or canvas alt
- **Border:** 0.5px `#303b452e` between cells
- **Use for:** social proof, product metrics, company scale

### 5. Product card grid (suite overview)

- **Grid:** 2×2 or 3×2, each card uses product hero gradient as background
- **Each card:** product icon (top) + category eyebrow (Gold caps) + product name (white 700) + one-line description + "Explore →" link (Gold)
- **Card radius:** 12px
- **Use for:** full suite overview, product comparison intro

### 6. Feature three-up

- **Grid:** 3 equal columns
- **Each column:** icon (Tabler outline, product accent color, 32px) → short bold label (Inter 600, 16pt) → 2–3 sentence description (Inter 400, 14pt, muted)
- **Background:** white or surface-raised
- **Use for:** three key benefits, three steps, three differentiators

### 7. Quote / testimonial

- **Layout:** centered, constrained width (~60% of slide)
- **Quote mark:** large Gold `"` character, decorative, 80pt
- **Quote text:** Inter 400 italic, 22–26pt, dark or white
- **Attribution:** Inter 500, 14pt, muted — Name · Company
- **Background:** canvas or dark navy
- **Use for:** customer proof, partner testimonials

---

## Typography for Slides

All slides use **Inter** exclusively. Embed weights 400, 600, and 800 minimum.

| Slide element | Size (pt) | Weight | Notes |
|--------------|-----------|--------|-------|
| Cover headline | 48–60 | 800 | Sentence case, ≤2 lines |
| Section headline | 36–44 | 800 | Sentence case |
| Content H2 | 28–32 | 800 | Sentence case |
| Eyebrow label | 10–11 | 600 | ALL CAPS, 0.08–0.1em letter spacing, Gold |
| Body text | 14–16 | 400 | Line height 1.5 |
| Stat number | 60–100 | 800 | — |
| Stat label | 11–13 | 500 | ALL CAPS, 0.08em spacing |
| Caption / footnote | 10–11 | 400 | Muted color |
| Button text | 12–14 | 700 | Title case |

### Emphasis pattern

The key ScalePad typographic move: a dark headline with **one or two Gold words** inline.

```
"Invisible work doesn't build trust. [Visible impact] does."
"[driving business outcomes]" — Gold shimmer gradient
```

In PPTX, render the Gold word as a separate text run with color `#eba900`. For the shimmer effect on cover slides, use a thin Gold underline as a proxy since PPTX doesn't support text gradients natively.

---

## Copywriting & Tone

ScalePad's voice is **confident, direct, and outcome-focused**. Every slide should feel like it was written for MSPs who are short on time and allergic to vague vendor claims.

### Patterns to follow

| Element | Pattern | Example |
|---------|---------|---------|
| Eyebrow | 2–3 word category label | `THE PROBLEM` · `THE PLATFORM` · `WHY SCALEPAD` |
| Headline | Short, punchy, one idea | "Invisible work doesn't build trust." |
| Gold emphasis | One key phrase per headline | "Visible **impact** does." |
| Body | Plain language, specific claims | "63+ frameworks. 40+ evidence integrations." |
| Stats | Number + short label | "74K+ · QBR HOURS SAVED" |
| CTA | Action verb + arrow | "Book a Demo →" · "Explore Pricing →" |

### Sentence case rules

- **Headlines:** Sentence case, no terminal punctuation (unless it's a question or the period is dramatic)
- **Eyebrows:** ALL CAPS always
- **Buttons/CTAs:** Title Case
- **Body text:** Normal sentence case with punctuation

### Product taglines (use verbatim on product slides)

| Product | Tagline |
|---------|---------|
| Lifecycle Manager | "Your operating system for the MSP to MVP journey." |
| ControlMap | "Run your compliance programs at MSP scale." |
| Quoter | "From proposal to payment in one motion." |
| Backup Radar | "Backup truth without the noise." |
| Cognition360 | "Business intelligence for clearer MSP performance." |
| ScalePad suite | "The MSP operating system for driving business outcomes." |

---

## Themes

### Dark theme (recommended: sales, launch, partner decks)

| Element | Value |
|---------|-------|
| Slide background | `#0a1c2b` (Navy) |
| Body text | `#ffffff` |
| Muted text | `rgba(255,255,255,0.7)` |
| Surface / card | `rgba(255,255,255,0.08)` |
| Border | `rgba(230,235,239,0.12)` |
| Accent | Product token (e.g., `#4ba384` for LM) |
| CTA button | `#eba900` fill, `#0a1c2b` text |

### Light theme (recommended: board, internal, data-heavy decks)

| Element | Value |
|---------|-------|
| Slide background | `#f5f7f9` |
| Alternate background | `#e5ebf0` |
| Body text | `#132435` |
| Muted text | `rgba(69,82,94,0.78)` |
| Surface / card | `rgba(255,255,255,0.78)` |
| Border | `rgba(48,59,69,0.11)` |
| Accent | Product token |
| CTA button | `#eba900` fill, `#0a1c2b` text |

---

## Illustration Style

When using decorative imagery (resource cards, playbook covers, learning series):

- **Style:** Flat line-art characters with solid fill shapes — not photorealistic
- **Palette:** Gold (`#eba900`), teal-green (`#3b8e62`), navy, white outlines on product-colored backgrounds
- **Characters:** simple, friendly, action-oriented (running, climbing, pointing) in muted navy/teal tones
- **Geometric accents:** floating square/rectangle blocks in the product accent color at various opacities
- **No gradients on illustrations** — flat fills only
- **Photography:** when used (Quoter page), always has product UI overlaid at an angle with floating product icon blocks. Never raw photography alone.

---

## Slide Dimension & Margins

| Setting | Value |
|---------|-------|
| Slide size | 13.33" × 7.5" (widescreen 16:9) |
| Safe margin | 0.5" all sides |
| Content area | 12.33" × 6.5" |
| Logo placement | Bottom-left at 0.25" from edge |
| Slide number | Bottom-right at 0.25" from edge, 10pt, muted |

---

## Common Slide Sequence (Sales Pitch)

A well-structured 10-slide ScalePad sales pitch follows this pattern:

1. **Cover** — full-bleed product hero, product logo, headline + Gold emphasis word
2. **Agenda** — light canvas, 3–4 numbered items, clean and minimal
3. **The problem** — two-column: bold statement left, relevant screenshot/data right
4. **Stats / social proof** — stat grid, 3–4 numbers with labels
5. **Product overview** — full-bleed section divider with product gradient
6. **Key capability 1** — two-column feature slide
7. **Key capability 2** — two-column feature slide
8. **Key capability 3** — three-up feature grid
9. **Customer quote** — centered testimonial on dark or canvas background
10. **Closing / CTA** — dark hero, Gold headline, "Book a Demo →" button, ScalePad logo

---

## AI Prompt Template

When calling Claude to build a ScalePad deck, include this reference:

```
Fetch the ScalePad design system from:
https://raw.githubusercontent.com/tulsie-narine/scalepad-design-style/main/scalepad-design-system.md

And the deck guide from:
https://raw.githubusercontent.com/tulsie-narine/scalepad-design-style/main/scalepad-deck-guide.md

Then build a [THEME] ScalePad deck for [PRODUCT/AUDIENCE] with [N] slides.
```

---

*Last updated: June 2026 · Source: live extraction from scalepad.com*  
*Companion file: `scalepad-design-system.md`*
