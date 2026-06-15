# ScalePad Design Style Guide

A living design reference for ScalePad-branded work — extracted directly from [scalepad.com](https://www.scalepad.com) and maintained for use across documents, decks, PDFs, and UI projects.

---

## Files in this repo

### [`scalepad-design-system.md`](./scalepad-design-system.md)
The core design system — colors, typography, CSS tokens, product gradients, buttons, status indicators, spacing, and border radius. The source of truth for any branded output.

### [`scalepad-deck-guide.md`](./scalepad-deck-guide.md)
PowerPoint/presentation-specific guide covering everything needed to build on-brand decks:
- Logo asset URLs (master, product lockups, product icons, compliance badges)
- Product color tokens (`--color-product-lm`, `--color-product-cm`, etc.) with hex values
- Product hero gradients (exact values for slide cover backgrounds)
- Seven slide layout patterns mapped from the website
- Typography scale for slides (pt sizes, weights, casing rules)
- Copywriting tone and product taglines
- Dark and light theme specs
- Illustration style guidance
- Standard 10-slide sales pitch sequence
- AI prompt template for calling Claude to build a deck

---

## Who this is for

This reference is built for anyone producing ScalePad-branded materials:

- **Solutions Engineers** building partner-facing field guides, compliance PDFs, and enablement decks
- **Developers** building ScalePad-integrated tools, portals, or demo environments
- **Designers** creating new collateral who need exact hex values, gradient specs, or token names
- **AI-assisted workflows** — structured so it can be fetched by Claude or other AI tools to automatically apply on-brand styling without manual lookups

---

## How to use it

### In an AI-assisted session

Point Claude at the raw file URLs to load the design system into context:

```
# Core design system (colors, typography, tokens)
https://raw.githubusercontent.com/tulsie-narine/scalepad-design-style/main/scalepad-design-system.md

# Deck/presentation guide (layouts, logos, product tokens)
https://raw.githubusercontent.com/tulsie-narine/scalepad-design-style/main/scalepad-deck-guide.md
```

Example prompt:
> "Fetch the ScalePad deck guide from my GitHub and build a 10-slide dark-theme pitch deck for ControlMap targeting MSP owners."

### In a CSS file

Copy the `:root {}` block from `scalepad-design-system.md` directly into your stylesheet.

### In a document or PDF pipeline

Reference the typography table and CSS variables when writing HTML templates for Playwright/Chromium rendering. Load Inter (woff2, weights 300–900) from your local fonts directory.

---

## Source & methodology

Tokens were extracted live from [scalepad.com](https://www.scalepad.com) using browser automation (Claude in Chrome + JavaScript CSS inspection) in June 2026. Values pulled from:

- Computed `:root` CSS custom properties
- Computed styles on key elements (headings, body, buttons, nav)
- Background gradients on all five product hero sections
- Product-specific CSS tokens (`--color-product-*`)
- SVG asset URL patterns from the live DOM

---

## Maintenance

When ScalePad updates their brand, re-run the extraction and update both files. Key things to re-check:

1. `:root` CSS variables on scalepad.com
2. Product color tokens (`--color-product-*`)
3. Product hero gradients (check all five product pages)
4. Logo asset URLs (pattern: `/scalepad-logo.svg`, `/product-logos/*.svg`, `/product-icons/*.svg`)
5. Any new product additions to the suite

---

*Maintained by Tulsie Narine · ScalePad Solutions Engineering*  
*Last extracted: June 2026*
