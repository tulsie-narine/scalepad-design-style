# ScalePad PowerPoint Deck Guide

> Extracted live from scalepad.com — June 2026  
> Companion to `scalepad-design-system.md`. Purpose-built for slide deck production.

---

## The #1 rule: slides are not webpages

The screenshots from the current build show the core problem — content is being laid out
like a website: small text, packed information, no breathing room. A presentation deck
operates on completely different principles.

| Web page | Presentation slide |
|----------|--------------------|
| User reads at their own pace | Audience sees it for 30–60 seconds |
| Text at 14–16px | Text at 28–60pt minimum |
| Dense information grids | One idea per slide |
| Full-width data tables | Large stats, bold labels |
| Decorative graphics optional | Visual anchors mandatory |
| Scroll for more | Cut — use more slides |

**If a slide has more than 40 words of body text, split it.  
If a stat is smaller than 48pt, make it bigger.  
If a slide has no graphic element, add one.**

---

## Quick-start checklist

Before building any ScalePad deck, confirm:

- [ ] Theme: **dark** (sales, launch, partner) or **light** (board, internal, data-heavy)
- [ ] Primary product accent (see token table below)
- [ ] Slide count: 8–14 sales pitch · 10–18 all-hands · 6–10 launch/announcement
- [ ] Font Inter embedded (not referenced) — weights 400, 600, 800
- [ ] Logo variant matches theme (white on dark, dark on light)
- [ ] Every slide has at least one graphic element (icon, shape, screenshot, illustration)
- [ ] No slide has more than 6 bullet points — split if needed
- [ ] Minimum body text 24pt — headline 40pt+

---

## Slide canvas specs

| Setting | Value |
|---------|-------|
| Size | 13.33" × 7.5" (widescreen 16:9) |
| Safe zone margin | 0.6" all sides |
| Content area | 12.13" × 6.3" |
| Logo: bottom-left | 0.25" from edge, 1.2" wide |
| Slide number: bottom-right | 0.25" from edge, 10pt, muted |
| Date: bottom-center | 10pt, muted (optional) |

---

## Typography for slides — minimum sizes

Web font sizes do not translate to slides. These are the floor, not the ceiling.

| Slide element | Min size (pt) | Weight | Case | Notes |
|--------------|---------------|--------|------|-------|
| Cover headline | 52–72 | 800 | Sentence | Max 8 words, 2 lines |
| Section headline | 44–56 | 800 | Sentence | Max 10 words |
| Content H1 | 36–44 | 800 | Sentence | Max 12 words |
| Content H2 / subhead | 24–28 | 600 | Sentence | Max 20 words |
| Eyebrow label | 12–14 | 600 | ALL CAPS | 0.1em spacing, Gold |
| Body / bullet text | 20–24 | 400 | Sentence | Max 15 words per line |
| Stat number | 64–120 | 800 | — | Should dominate the slide |
| Stat label | 13–16 | 500 | ALL CAPS | 0.08em spacing, muted |
| Table cell text | 18–22 | 400–600 | — | Never smaller |
| Caption / footnote | 12–14 | 400 | — | Absolute minimum |
| Button / CTA text | 16–18 | 700 | Title Case | — |

**The Gold emphasis word** — one key phrase per headline in Gold `#eba900`.
In PPTX render as a separate text run. On cover slides add a thin Gold underline
as a proxy for the shimmer gradient (PPTX doesn't support text gradients natively).

---

## Graphic elements — every slide needs at least one

Slides without visual anchors look unfinished. These are the building blocks:

### 1. Large background watermark icon
- Product icon SVG at 35–50% of slide height, 8–15% opacity
- Placed bottom-right or center-right, overlapping the edge
- Color: white on dark themes, navy on light themes
- This is the most important element missing from the current build

### 2. Color accent panel / sidebar
- A solid rectangle in the product accent color, 1.5–2" wide, full slide height (left or right edge)
- Or a horizontal band at the bottom, 0.8–1.2" tall
- Creates instant visual structure and brand color presence
- Use on content slides, section slides, table slides

### 3. Abstract geometric shapes
- Circles, partial arcs, or diagonal cuts in the product gradient at 15–25% opacity
- Placed at corners or bleeding off the slide edge
- Adds depth without competing with content

### 4. Product screenshot / mockup
- Always placed in a white rounded-rect card with a soft shadow
- Float it — never fill the entire slide with a screenshot
- Crop aggressively to show only the relevant part of the UI
- Scale: 40–55% of slide width for two-column layouts

### 5. Full-bleed illustration (cover / section only)
- Occupies 50–60% of the slide (right half)
- ScalePad illustration style: flat line-art, Gold + teal fills, navy outlines
- Never stretch or distort — use as a hero visual

### 6. Stat callout box
- Colored rounded rectangle (product accent, 10–15% opacity fill, full-color border)
- Contains stat number (64–80pt/800) + label (13pt/500/caps) + optional trend arrow
- Minimum 2.5" × 1.8" — large enough to read from the back of a room

---

## Layout patterns — the 8 slide types

### TYPE 1 — Cover slide

```
┌─────────────────────────────────────────────────────┐
│  [Product gradient full-bleed background]           │
│                                                     │
│         [Product logo — white, centered, 2.5" wide] │
│                                                     │
│    Headline in white, 60–72pt/800, centered         │
│    [Gold emphasis word] in same line                │
│                                                     │
│    Subhead, white/70%, 22pt/400, centered           │
│                                                     │
│    [Gold CTA button]  [White-outline button]        │
│                                                     │
│    [Watermark icon, 40% height, 10% opacity, BR]    │
│  SCALEPAD logo (BL)              Date · Slide # (BR)│
└─────────────────────────────────────────────────────┘
```

### TYPE 2 — Section divider

```
┌─────────────────────────────────────────────────────┐
│  [Full-bleed product accent color]                  │
│                                                     │
│  ── thin white hairline rule ──                     │
│                                                     │
│  EYEBROW LABEL  12pt/600/caps/Gold                  │
│  Section headline  52pt/800/white                   │
│  One-sentence context  22pt/400/white 70%           │
│                                                     │
│  [Large abstract circle, 15% opacity, right bleed]  │
│  SCALEPAD (BL)                          Slide # (BR)│
└─────────────────────────────────────────────────────┘
```

### TYPE 3 — Two-column: statement + visual

The workhorse layout. Left = headline + body. Right = screenshot or illustration.

```
┌───────────────────┬─────────────────────────────────┐
│ [Accent panel     │  [White card, rounded, shadow]  │
│  left edge 0.3"]  │   Product screenshot inside     │
│                   │   cropped to key feature        │
│ EYEBROW  12pt/600 │                                 │
│                   │  [Floating stat callout box     │
│ Headline          │   overlapping card corner]      │
│ 40pt/800          │                                 │
│ max 2 lines       │                                 │
│                   │                                 │
│ Body text         │                                 │
│ 22pt/400          │                                 │
│ max 3 lines       │                                 │
│                   │                                 │
│ • Bullet  22pt    │                                 │
│ • Bullet  22pt    │                                 │
│ • Max 3 bullets   │                                 │
│                   │                                 │
│ Explore → 16pt    │                                 │
│ Gold/underline    │                                 │
│                   SCALEPAD (BL)       Slide # (BR)  │
└───────────────────┴─────────────────────────────────┘
```

### TYPE 4 — Stat hero (single metric)

One number. Full slide. This is not a four-column grid at 48pt — it's one number at 120pt.

```
┌─────────────────────────────────────────────────────┐
│  [Dark navy or product gradient background]         │
│                                                     │
│  EYEBROW LABEL  12pt/600/Gold/caps                  │
│                                                     │
│           [Stat number  96–120pt/800/white]         │
│           STAT LABEL  16pt/500/muted/caps           │
│                                                     │
│  Supporting context line, 22pt/400/white 60%        │
│                                                     │
│  [Watermark icon, 50% height, 8% opacity]           │
│  SCALEPAD (BL)                          Slide # (BR)│
└─────────────────────────────────────────────────────┘
```

### TYPE 5 — Stat grid (2-up or 3-up MAX)

Web layouts use 4-up grids. Decks use 2-up or 3-up — never 4. Each stat needs room to breathe.

```
┌───────────────────────┬─────────────────────────────┐
│  EYEBROW  14pt/600    │  EYEBROW  14pt/600           │
│                       │                             │
│  $94.5K               │  $8.4K/mo                   │
│  72pt/800/Gold        │  72pt/800/white             │
│                       │                             │
│  CAPEX ONE-TIME       │  MONTHLY RECURRING          │
│  14pt/500/muted/caps  │  14pt/500/muted/caps        │
│                       │                             │
│  Across 12 initiatives│  → $100.8K annualized       │
│  18pt/400/muted       │  18pt/400/muted             │
└───────────────────────┴─────────────────────────────┘
│  SCALEPAD (BL)  [Product badge, center]  Slide # (BR)│
└─────────────────────────────────────────────────────┘
```

### TYPE 6 — Data table

Tables on slides need chunky row heights and large type. The current build has 12pt table text — that is unreadable from 6 feet away.

```
Column headers: 14pt/600/caps/muted  — background: accent color 20% opacity
Data rows:      20–22pt/400/white    — row height minimum 0.45"
Status pills:   12pt/600            — colored rounded rect, NOT text-only
Amount column:  22pt/700/white       — right-aligned, bold
Alternating rows: 0 and 5% white opacity for zebra striping
```

Status pill colors (matching scalepad.com):
- **In progress** → `rgba(235,169,0,0.2)` fill, `#eba900` text
- **Approved** → `rgba(59,142,98,0.2)` fill, `#4ba384` text
- **Proposed** → `rgba(255,255,255,0.1)` fill, `rgba(255,255,255,0.6)` text
- **On hold** → `rgba(169,66,35,0.2)` fill, `#e07050` text

### TYPE 7 — Three-up feature grid

Three equal cards, each with a large icon, label, and 2-sentence description.

```
Each card:
  - Icon: 40px, product accent color (not muted — full color)
  - Label: 22pt/700, white or dark
  - Description: 18pt/400, muted, max 2 lines
  - Card: rounded 12px, surface fill (8% white), accent-color border 1px
  - Card size: ~3.8" × 2.8"
  - Gap between cards: 0.25"
```

### TYPE 8 — Quote / testimonial

```
┌─────────────────────────────────────────────────────┐
│  [Dark background or accent panel left 35%]         │
│                                                     │
│  " ← 80pt/800/Gold decorative quote mark            │
│                                                     │
│  "Quote text in sentence case,                      │
│   28pt/400/italic/white,                            │
│   max 3 lines, constrained to 65% width"            │
│                                                     │
│  ── Gold hairline rule, 2" wide ──                  │
│                                                     │
│  Name · Company  18pt/500/muted                     │
│                                                     │
│  [Avatar circle, 56px, accent bg, initials]  (left) │
│  SCALEPAD (BL)                          Slide # (BR)│
└─────────────────────────────────────────────────────┘
```

---

## What the current build is getting wrong (and how to fix it)

### Problem 1: Text is too small

**Current:** 14–16pt body, 24–32pt headlines, 10pt labels  
**Fix:** Floor is 20pt body, 40pt headlines, 12pt labels. Use fewer words, not smaller type.

### Problem 2: No background graphic element

**Current:** Flat color background, no watermark, no shapes  
**Fix:** Add a large product icon as a watermark (35–45% slide height, 8–12% opacity) on every dark slide. Add abstract circles/arcs bleeding off edges.

### Problem 3: 4-up stat grids at small scale

**Current:** 4 stats across with 48pt numbers in tight cells  
**Fix:** Use 2-up grids at 72pt minimum. If you have 4 stats, use two slides or a 2+2 staggered layout with more breathing room.

### Problem 4: Tables look like spreadsheets

**Current:** Compact rows, small text, text-only status indicators  
**Fix:** Minimum 0.45" row height, 20pt cell text, color-pill status badges, bold amount column.

### Problem 5: No color accent panel

**Current:** Content floats on a flat background with no structural anchoring  
**Fix:** Add a 0.3" product accent sidebar on the left edge of all content slides (dark theme). Or a bottom band. This is the single fastest fix to make slides look designed.

### Problem 6: One slide is doing two jobs

**Current:** Initiative roadmap table + status summary + CapEx chart on same visual  
**Fix:** Split into: (a) roadmap table slide, (b) CapEx chart slide, (c) summary stats slide.

---

## Product color tokens (from live CSS)

| Product | CSS var | Hex | Deck accent use |
|---------|---------|-----|----------------|
| Lifecycle Manager | `--color-product-lm` | `#4ba384` | Teal-green |
| Lifecycle Insights | `--color-product-lci` | `#007674` | Deep teal |
| ControlMap | `--color-product-cm` | `#693568` | Deep purple |
| Quoter | `--color-product-qt` | `#b71e74` | Magenta-pink |
| Backup Radar | `--color-product-br` | `#216092` | Deep blue |
| Cognition360 | `--color-product-c360` | `#cf304c` | Deep red |
| Platform | `--color-platform-accent` | `#8f96ff` | Indigo |

### Product hero gradients (for cover / section slides)

| Product | Gradient |
|---------|----------|
| Lifecycle Manager | `linear-gradient(45deg, #022620, #1a4f40, #4ba384)` |
| ControlMap | `linear-gradient(45deg, #24122d, #693568, #9e579e)` |
| Quoter | `linear-gradient(45deg, #3d0e2d, #a0295a, #e0608e)` |
| Backup Radar | `linear-gradient(45deg, #0b1e38, #1a4a7a, #4a8fc4)` |
| Cognition360 | `linear-gradient(45deg, #6d2536, #b92e47, #fe7780)` |
| ScalePad suite | `linear-gradient(135deg, #0d1f30, #42436c)` with radial overlay |

Overlay applied to all hero gradients:
```
radial-gradient(circle at 88% 8%, rgba(255,255,255,0.13), transparent 34%)
+ linear-gradient(45deg, rgba(0,0,0,0.26), transparent 70%)
```

---

## Logo & asset URLs

| Asset | URL |
|-------|-----|
| ScalePad logo | `https://www.scalepad.com/scalepad-logo.svg` |
| Lifecycle Manager logo | `https://www.scalepad.com/product-logos/lifecycle-manager.svg` |
| Lifecycle Manager white | `https://www.scalepad.com/product-logos/lifecycle-manager-white.svg` |
| ControlMap logo | `https://www.scalepad.com/product-logos/controlmap.svg` |
| ControlMap white | `https://www.scalepad.com/product-logos/controlmap-white.svg` |
| Quoter logo | `https://www.scalepad.com/product-logos/quoter.svg` |
| Quoter white | `https://www.scalepad.com/product-logos/quoter-white.svg` |
| Backup Radar logo | `https://www.scalepad.com/product-logos/backup-radar.svg` |
| Backup Radar white | `https://www.scalepad.com/product-logos/backup-radar-white.svg` |
| Cognition360 logo | `https://www.scalepad.com/product-logos/cognition360.svg` |
| Cognition360 white | `https://www.scalepad.com/product-logos/cognition360-white.svg` |
| LM icon | `https://www.scalepad.com/product-icons/lifecycle-manager.svg` |
| ControlMap icon | `https://www.scalepad.com/product-icons/controlmap.svg` |
| Quoter icon | `https://www.scalepad.com/product-icons/quoter.svg` |
| Backup Radar icon | `https://www.scalepad.com/product-icons/backup-radar.svg` |
| Cognition360 icon | `https://www.scalepad.com/product-icons/cognition360.svg` |
| SOC 2 Type II badge | `https://www.scalepad.com/compliance/soc-2-type-ii.svg` |
| ISO 27001 badge | `https://www.scalepad.com/compliance/iso-27001.svg` |

**Logo usage on slides:**
- Dark backgrounds: always use white variant
- Light backgrounds: use color/default variant
- Never recolor, never stretch, always maintain aspect ratio
- Minimum logo width on slide: 1.0" (SCALEPAD footer) · 2.0" (hero product logo)
- Clearspace: equal to cap-height of the "S" on all four sides

---

## Themes

### Dark theme (sales, launch, partner decks)

| Element | Value |
|---------|-------|
| Background | `#0a1c2b` |
| Alt surface / card fill | `rgba(255,255,255,0.06)` |
| Card border | `rgba(255,255,255,0.12)` |
| Body text | `#ffffff` |
| Muted text | `rgba(255,255,255,0.60)` |
| Subtle text | `rgba(255,255,255,0.38)` |
| Accent | Product token (e.g. `#4ba384` for LM) |
| Gold CTA | `#eba900` fill · `#0a1c2b` text |
| Watermark icon opacity | 8–12% |

### Light theme (board, internal, data-heavy)

| Element | Value |
|---------|-------|
| Background | `#f5f7f9` |
| Alt background | `#e5ebf0` |
| Card fill | `rgba(255,255,255,0.78)` |
| Card border | `rgba(48,59,69,0.11)` |
| Body text | `#132435` |
| Muted text | `rgba(69,82,94,0.78)` |
| Accent | Product token |
| Gold CTA | `#eba900` fill · `#0a1c2b` text |

---

## Copywriting patterns

| Element | Pattern | Example |
|---------|---------|---------|
| Eyebrow | 2–3 word category, ALL CAPS | `THE PROBLEM` · `WHY SCALEPAD` |
| Headline | Short, punchy, one idea | "Invisible work doesn't build trust." |
| Gold word | One key phrase inline | "Visible **impact** does." |
| Stats | Big number + short label | "74K+ · QBR HOURS SAVED" |
| Bullets | Max 3–4, max 12 words each | "63 frameworks. 40+ evidence integrations." |
| CTA | Action verb + arrow | "Book a Demo →" |

### Sentence case rules
- **Headlines:** Sentence case, no terminal punctuation (unless dramatic)
- **Eyebrows:** ALL CAPS always
- **CTAs:** Title Case
- **Bullets:** Sentence case with no period

### Product taglines (use verbatim)

| Product | Tagline |
|---------|---------|
| Lifecycle Manager | "Your operating system for the MSP to MVP journey." |
| ControlMap | "Run your compliance programs at MSP scale." |
| Quoter | "From proposal to payment in one motion." |
| Backup Radar | "Backup truth without the noise." |
| Cognition360 | "Business intelligence for clearer MSP performance." |
| ScalePad | "The MSP operating system for driving business outcomes." |

---

## Standard 10-slide sales pitch sequence

| # | Type | Content |
|---|------|---------|
| 1 | Cover | Product hero, logo, headline + Gold word, date |
| 2 | Stat hero | Single most impressive number (e.g. 8,000+ MSPs) |
| 3 | Section divider | "The problem" — product accent background |
| 4 | Two-column | Problem statement + screenshot showing the pain |
| 5 | Two-column | Solution / key capability 1 + UI screenshot |
| 6 | Three-up cards | Three key benefits with icons — NOT bullets |
| 7 | Stat grid (2-up) | Two ROI/impact stats at 72pt |
| 8 | Quote | Customer testimonial — single quote, large |
| 9 | Two-column | Next steps / pricing overview |
| 10 | Closing/Cover | Dark hero, "Book a Demo →" CTA, full ScalePad logo |

---

## AI prompt template

```
Fetch the ScalePad deck guide:
https://raw.githubusercontent.com/tulsie-narine/scalepad-design-style/main/scalepad-deck-guide.md

Build a [dark/light] ScalePad deck for [PRODUCT] targeting [AUDIENCE].
[N] slides. Use the layout types from the deck guide.

Strict requirements:
- Minimum 40pt headlines, 22pt body text, 72pt stat numbers
- Every slide must have a background watermark or accent panel
- Max 3 bullets per slide, max 12 words per bullet
- Status table rows minimum 0.45" height, 20pt text, color pill badges
- Split any slide with more than one main idea into two slides
```

---

*Last updated: June 2026 · Source: live extraction from scalepad.com + presentation design best practices*  
*Companion: `scalepad-design-system.md`*

---

## Enforcement addendum — hard floors for deck builders

> Added June 2026 after slide audit. These override any ranges elsewhere in this guide.  
> The build tool must treat these as non-negotiable minimums, not suggestions.

### Type size hard floors (pt)

| Element | MINIMUM | Typical | Never below |
|---------|---------|---------|-------------|
| Cover headline | **52pt** | 60pt | 40pt |
| Cover gold sub-headline | **44pt** | 52pt | 36pt |
| Section divider headline | **44pt** | 52pt | 36pt |
| Content slide H1 | **36pt** | 44pt | 28pt |
| Content slide H2 / subhead | **24pt** | 28pt | 20pt |
| Body / bullet text | **20pt** | 22pt | 16pt |
| Eyebrow label | **12pt** | 14pt | 11pt |
| Stat number | **72pt** | 80–96pt | 60pt |
| Stat label (caps) | **14pt** | 16pt | 12pt |
| Table cell text | **18pt** | 20pt | 14pt |
| Bottom footer (ScalePad, slide #) | **9pt** | 10pt | 8pt |

**Rule for builders:** when a range like "52–72pt" appears anywhere in this guide, always use the LOWER bound as the minimum and apply it. Do not pick the minimum of the range — pick the midpoint or higher.

### Illustration size hard floors (inches, 13.33" × 7.5" slide)

| Element | MINIMUM height | Placement |
|---------|---------------|-----------|
| Cover character | **4.1"** (55% of slide height) | Right 55% of slide, baseline 0.4" from bottom |
| Interior character | **3.5"** (47% of slide height) | Right half of slide |
| Abstract illustration (arrows, shapes) | **3.0"** | Right half OR centered watermark |
| Background watermark icon | **2.5"** | Bottom-right, 8–12% opacity |

### Cover slide: allowed / not allowed

| Allowed on cover | Not allowed on cover |
|-----------------|----------------------|
| Product logo (white, centered or top-left) | App/web action buttons (View, Export, Download) |
| Client/company name | Integration tags or platform badges |
| Document title (large, bold) | Metadata strings longer than 10 words |
| Gold emphasis sub-headline | Status indicators or progress chips |
| Date (bottom, small) | Navigation breadcrumbs |
| ScalePad logo + slide number (footer) | More than 2 CTA buttons |
| One short supporting line (max 12 words) | Bullet lists |
| Character illustration (right half) | Tables or data grids |

### Stat grid hard limit

- **Maximum 2 stats per row** on a single slide
- **Maximum 3 stats per slide** (use a 2+1 stacked layout)
- If you have 4 stats → use 2 slides, each with 2 stats
- Stat cards must have **minimum 16px vertical padding** inside
- Stat number and label must have **minimum 12px gap** between them

### Illustration placement rule

Characters always go in the **right 50–60% of the slide**, never left. Text always goes left. The character's feet land at 0.4–0.5" from the slide bottom. The character's head should not be clipped by the slide top edge.

Exception: cover slides may center the character if the headline occupies a full-width bottom band.

### No web UI on slides — prohibited elements

The following elements are web/app UI conventions and must **never appear on a slide**:

- Action buttons (View, Export, Download, Open, Submit)
- Integration/platform tag pills (Datto RMM, Autotask PSA, etc.) — unless on a dedicated "integrations" slide
- Navigation breadcrumbs or progress indicators
- Form inputs, dropdowns, checkboxes
- Pagination controls
- Toast notifications or alert banners
- Any element whose purpose is "click to do something"

**Only exception:** a single primary CTA button on a cover or closing slide ("Book a Demo →", "View Roadmap →") is acceptable as a visual design element — but must be styled as a presentation button (large, gold, 16pt text) not a web button (small, outlined, 13pt text).

### Chart slides — charts must actually render

If a slide includes a chart (bar, line, area):
- The chart must be built as a **native pptxgenjs chart object** — not an HTML canvas, not a placeholder, not a legend-only element
- Legend appears **above** the chart, not inside it
- Chart area minimum height: **3.0"**
- Axis labels: minimum **11pt**
- Data labels on bars: minimum **10pt**
- If the chart cannot be rendered natively, replace the slide with a stat grid showing the key data points instead

