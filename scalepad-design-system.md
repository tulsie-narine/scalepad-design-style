# ScalePad Design System Reference

> Extracted live from [scalepad.com](https://www.scalepad.com) · June 2026  
> Use this as a reference for all ScalePad-branded documents, decks, PDFs, and UI work.

---

## Typography

**Font family:** `Inter` (primary), `Inter Fallback`, `ui-sans-serif`, `system-ui`, `sans-serif`

| Role | Size | Weight | Line Height | Letter Spacing | Notes |
|------|------|--------|-------------|----------------|-------|
| H1 | 76px | 800 | 1.08 | normal | Hero headlines |
| H2 | 44px | 400 | 1.1 | -0.018em | Section headings |
| H3 | varies | 600 | 1.0 | normal | Sub-section |
| Eyebrow | 12px | 600 | — | 0.1em | ALL CAPS, Gold color |
| Body | 16px | 400 | 1.5 | normal | Default text |
| Label / Stat | 13px | 500 | — | normal | Captions, stat labels |

---

## Core Color Palette

### Brand Colors

| Token | Hex | Usage |
|-------|-----|-------|
| `--color-navy` | `#0a1c2b` | Primary brand dark, nav background |
| `--color-site-foreground` | `#132435` | Body text color |
| `--color-gold` | `#eba900` | CTA buttons, emphasis, eyebrow labels |
| `--color-gold-hover` | `#f5b820` | CTA hover state |
| `--color-green` | `#3b8e62` | Success, accent (dark mode hero) |
| `--color-site-accent` | `#327b57` | Link focus, accent borders |
| `--color-site-accent-hover` | `#286747` | Accent hover |

### Surface & Layout

| Token | Hex | Usage |
|-------|-----|-------|
| `--color-site-canvas` | `#f5f7f9` | Page background (light mode) |
| `--color-site-canvas-alt` | `#e5ebf0` | Alternate section background |
| `--color-site-surface` | `#ffffffc7` | Card surface |
| `--color-site-surface-raised` | `#fffffff0` | Elevated card / modal |
| `--color-site-surface-muted` | `#ebf0f4d1` | Muted/disabled surface |
| `--color-site-overlay` | `#fffffffa` | Overlay background |

### Text & Muted

| Token | Value | Usage |
|-------|-------|-------|
| `--color-site-muted` | `#45525ec7` | Secondary/muted text |
| `--color-site-subtle` | `#54616d9e` | Hint / placeholder text |
| `--color-site-emphasis` | `#d19700` | Emphasized inline text |
| `--color-site-link` | `#0a1c2b` | Link color (= Navy) |
| `--color-site-link-hover` | `color-mix(in srgb, #0a1c2b 72%, ...)` | Link hover |

### Borders & Shadows

| Token | Value | Usage |
|-------|-------|-------|
| `--color-site-border` | `#303b451c` | Default border |
| `--color-site-border-strong` | `#303b452e` | Emphasized border |
| `--color-site-shadow` | `#29333d1a` | Subtle shadow |
| `--color-site-shadow-strong` | `#29333d2e` | Elevated shadow |

### Semantic

| Token | Hex | Usage |
|-------|-----|-------|
| `--color-site-success` | `#327b57` | Success state |
| `--color-site-warning` | `#d19600` | Warning state |
| `--color-site-danger` | `#a94223` | Error / danger state |
| `--color-site-focus` | `#317d57` | Focus ring |

---

## CTA Emphasis Gradient

Used for gold shimmer text on hero headlines (e.g. *"driving business outcomes"*):

```css
background: linear-gradient(90deg, #fbe49f 0%, #ffca05 50%, #f5aa1b 100%);
-webkit-background-clip: text;
-webkit-text-fill-color: transparent;
background-clip: text;
```

---

## Product Accent Gradients

Each product has a signature dark-to-light gradient used on product cards and landing pages.

| Product | Category | Gradient |
|---------|----------|----------|
| **Lifecycle Manager** | Customer Success Platform | `linear-gradient(45deg, #022620 0%, #1a4f40 56%, #4ba384 100%)` |
| **ControlMap** | Compliance, vCISO & GRC | `linear-gradient(45deg, #24122d 0%, #693568 56%, #9e579e 100%)` |
| **Quoter** | CPQ & Quote-to-Cash | `linear-gradient(45deg, #3d0e2d 0%, #a0295a 56%, #e0608e 100%)` |
| **Backup Radar** | Backup SLA & Compliance | `linear-gradient(45deg, #0b1e38 0%, #1a4a7a 56%, #4a8fc4 100%)` |
| **Cognition360** | BI for ConnectWise | `linear-gradient(45deg, #2a1012 0%, #7a2020 56%, #c45050 100%)` |

### Product Colors (Computed)

| Product | Primary Hue | Hex Approx |
|---------|-------------|------------|
| Lifecycle Manager | Deep teal-green | `#1a4f40` |
| ControlMap | Deep purple | `#693568` |
| Quoter | Deep magenta-pink | `#a0295a` |
| Backup Radar | Deep blue | `#1a4a7a` |
| Cognition360 | Deep red | `#7a2020` |

---

## Dark Mode (Hero / Demo Pages)

The dark hero uses `--color-navy` (`#0a1c2b`) as the canvas with these overrides:

```css
--color-site-canvas:        var(--color-navy);
--color-site-canvas-alt:    #081521;
--color-site-surface:       #ffffff08;
--color-site-surface-raised:#ffffff0d;
--color-site-border:        #e6ebef1f;
--color-site-foreground:    #ffffff;
--color-site-muted:         #d9e0e8b3;
--color-site-subtle:        #d9e0e87a;
--color-site-focus:         #ffbd14;
```

### Background Artwork Gradient (dark sections)

```css
background: radial-gradient(circle at 74% 18%, #5c5fbcb3, transparent 42%),
            linear-gradient(135deg, #1a2f42, #545796);
```

---

## Status Indicators

| State | Background | Border | Text | Dot |
|-------|-----------|--------|------|-----|
| Success | `rgba(50,123,87, 0.14)` | `rgba(50,123,87, 0.34)` | `color-mix(#327b57 74%, #132435)` | `#327b57` |
| Warning | `rgba(209,150,0, 0.16)` | `rgba(209,150,0, 0.38)` | `color-mix(#d19600 64%, #132435)` | `#d19600` |

---

## Buttons

| Variant | Background | Text Color | Border | Border Radius |
|---------|-----------|------------|--------|---------------|
| Primary (CTA) | `#eba900` | `#0a1c2b` (Navy) | none | `6px` |
| Primary hover | `#f5b820` | `#0a1c2b` | none | `6px` |
| Secondary | transparent | `#132435` | `1.5px solid #303b452e` | `6px` |
| Dark | `#0a1c2b` | `#ffffff` | none | `6px` |

**CTA button font:** Inter, 14px, weight 700  
**Secondary font:** Inter, 14px, weight 500

---

## Spacing Scale

| Token | Value |
|-------|-------|
| xs | 4px |
| sm | 8px |
| md | 12px |
| lg | 16px |
| xl | 24px |
| 2xl | 32px |
| 3xl | 48px |
| 4xl | 64px |

---

## Border Radius

| Usage | Value |
|-------|-------|
| Inputs, small elements | `4px` |
| Buttons | `6px` |
| Cards | `8–12px` |
| Pills / badges | `99px` |

---

## CSS Variables — Quick Reference

```css
:root {
  /* Brand */
  --color-navy:               #0a1c2b;
  --color-gold:               #eba900;
  --color-gold-hover:         #f5b820;
  --color-green:              #3b8e62;

  /* Site tokens (light mode) */
  --color-site-canvas:        #f5f7f9;
  --color-site-canvas-alt:    #e5ebf0;
  --color-site-foreground:    #132435;
  --color-site-muted:         #45525ec7;
  --color-site-subtle:        #54616d9e;
  --color-site-emphasis:      #d19700;
  --color-site-cta:           #eba900;
  --color-site-cta-hover:     #f5b820;
  --color-site-link:          #0a1c2b;
  --color-site-accent:        #327b57;
  --color-site-accent-hover:  #286747;
  --color-site-focus:         #317d57;
  --color-site-surface:       #ffffffc7;
  --color-site-surface-raised:#fffffff0;
  --color-site-surface-muted: #ebf0f4d1;
  --color-site-border:        #303b451c;
  --color-site-border-strong: #303b452e;
  --color-site-shadow:        #29333d1a;
  --color-site-shadow-strong: #29333d2e;
  --color-site-overlay:       #fffffffa;
  --color-site-success:       #327b57;
  --color-site-warning:       #d19600;
  --color-site-danger:        #a94223;
  --color-site-scrim:         #18263557;

  /* Typography */
  --font-inter: "Inter", "Inter Fallback";
}
```

---

## Usage Notes

- **Always pair Gold CTA (`#eba900`) with Navy (`#0a1c2b`) text** — the navy-on-gold combo is the primary brand CTA pattern.
- **Eyebrow labels** above headings use Gold + uppercase + 0.1em letter-spacing at 12px/600.
- **Hero sections** flip to dark mode (navy canvas, white foreground) regardless of system theme.
- **Product cards** always use their product gradient as background with white text on top.
- **Inter is the only typeface** — no display or serif fonts are used anywhere on the site.
- For PDF/HTML documents, load Inter from `/hipaa-guide/fonts/` (woff2, weights 300–900) to stay offline-safe.

---

*Last updated: June 2026 · Source: live CSS extraction from scalepad.com*
