# ScalePad Design Style Guide

A living design reference for ScalePad-branded work — extracted directly from [scalepad.com](https://www.scalepad.com) and maintained for use across documents, decks, PDFs, and UI projects.

---

## What's in this repo

### [`scalepad-design-system.md`](./scalepad-design-system.md)

A comprehensive design reference covering everything you need to produce on-brand ScalePad output:

- **Typography** — Inter font family with the full scale: H1 (76px/800) through body (16px/400), eyebrow labels, and stat captions
- **Core color palette** — all CSS custom property tokens for brand colors, surfaces, text, borders, shadows, and semantic states (success, warning, danger)
- **Product accent gradients** — the five signature dark-to-light gradients for Lifecycle Manager, ControlMap, Quoter, Backup Radar, and Cognition360
- **Dark mode tokens** — the navy-canvas hero overrides used on landing and demo pages
- **CTA emphasis gradient** — the gold shimmer used on hero headline text
- **Button variants** — Primary (Gold/Navy), Secondary, and Dark styles with exact colors, weights, and border radius
- **Status indicators** — success, warning, and danger chip styles with background, border, text, and dot colors
- **Spacing scale** — 4px through 64px
- **Border radius** — from 4px inputs to 99px pills
- **CSS quick-reference block** — all tokens in a single copyable `:root {}` block

---

## Who this is for

This reference is built for anyone producing ScalePad-branded materials:

- **Solutions Engineers** building partner-facing field guides, compliance PDFs, and enablement decks
- **Developers** building ScalePad-integrated tools, portals, or demo environments
- **Designers** creating new collateral who need exact hex values, gradient specs, or token names
- **AI-assisted workflows** — this file is structured so it can be fetched by Claude or other AI tools to automatically apply on-brand styling without manual lookups

---

## How to use it

### In a document or PDF pipeline

Reference the CSS variables block and typography table when writing HTML templates for Playwright/Chromium rendering. The Inter font (woff2, weights 300–900) should be loaded from your local fonts directory.

### In an AI-assisted session

Point Claude (or any AI tool) at the raw file URL to load the design system into context:

```
https://raw.githubusercontent.com/tulsie-narine/scalepad-design-style/main/scalepad-design-system.md
```

Example prompt:
> "Fetch the ScalePad design system from my GitHub and use it to style this HTML template."

### In a CSS file

Copy the `:root {}` block from the quick-reference section directly into your stylesheet.

---

## Source & methodology

The design tokens in this repo were extracted live from [scalepad.com](https://www.scalepad.com) using browser automation (Claude in Chrome + JavaScript CSS inspection) in June 2026. Values were pulled from:

- Computed `:root` CSS custom properties
- Computed styles on key elements (h1–h4, body, buttons, nav)
- Background gradients on product cards and hero sections

This means the values reflect what's actually shipping in production — not an older internal spec that may have drifted.

---

## Maintenance

When ScalePad updates their brand, re-run the extraction and update `scalepad-design-system.md`. The key things to re-check are:

1. `:root` CSS variables on scalepad.com
2. Product card gradients (the suite occasionally adds or rebrands products)
3. CTA button colors and typography weights
4. Any new product accent colors

---

*Maintained by Tulsie Narine · ScalePad Solutions Engineering*  
*Last extracted: June 2026*
