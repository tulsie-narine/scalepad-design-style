# ScalePad Design Style Guide

A living design reference for ScalePad-branded work — extracted directly from [scalepad.com](https://www.scalepad.com) and maintained for use across documents, decks, PDFs, and UI projects.

---

## Files in this repo

### [`scalepad-design-system.md`](./scalepad-design-system.md)
The core design system — colors, typography, CSS tokens, product gradients, buttons, status indicators, spacing, and border radius. The source of truth for any branded output.

### [`scalepad-deck-guide.md`](./scalepad-deck-guide.md)
PowerPoint/presentation-specific guide — slide layouts, typography sizes (presentation-first, not web), logo asset URLs, product color tokens, hero gradients, copywriting patterns, and a 10-slide sales pitch sequence. Includes a "what's going wrong and how to fix it" section for common build errors.

### [`scalepad-illustration-guide.md`](./scalepad-illustration-guide.md)
Illustration style guide — how to draw, prompt, or direct ScalePad-style characters, icons, and abstract graphics:
- Two illustration modes: character vs. abstract/geometric
- Character construction: anatomy, poses, gold hair rule, color palette
- Symbolic object library (shields, arrows, locks, laptops, etc.)
- Background system (solid product colors + watermark)
- AI image generation prompt templates (Midjourney, DALL-E, Firefly)
- SVG drawing instructions with exact stroke/fill settings
- Do/Don't reference table
- When to use illustrations vs. screenshots vs. product gradients

### [`scalepad-deck-SKILL.md`](./scalepad-deck-SKILL.md)
The `scalepad-deck` Claude skill file, updated with GitHub design reference links.

---

## Raw URLs for AI sessions

```
# Core design tokens (colors, typography, CSS vars)
https://raw.githubusercontent.com/tulsie-narine/scalepad-design-style/main/scalepad-design-system.md

# Deck/presentation guide (layouts, sizes, logos, product tokens)
https://raw.githubusercontent.com/tulsie-narine/scalepad-design-style/main/scalepad-deck-guide.md

# Illustration guide (characters, icons, AI prompts, SVG instructions)
https://raw.githubusercontent.com/tulsie-narine/scalepad-design-style/main/scalepad-illustration-guide.md
```

### Example prompts

**Build a deck:**
> "Fetch the ScalePad deck guide from GitHub and build a 10-slide dark-theme pitch deck for ControlMap targeting MSP owners."

**Generate an illustration:**
> "Fetch the ScalePad illustration guide from GitHub and generate an SVG character illustration for a slide about backup monitoring."

**Full brand context:**
> "Fetch all three ScalePad style guides from GitHub, then build a ControlMap product launch deck with on-brand illustrations on the cover and section divider slides."

---

## Who this is for

- **Solutions Engineers** — field guides, compliance PDFs, enablement decks
- **Developers** — branded tools, portals, demo environments
- **Designers** — hex values, gradient specs, illustration briefs
- **AI-assisted workflows** — structured for direct fetch-and-use by Claude or other AI tools

---

## Maintenance

When ScalePad updates their brand, re-run the extraction and update the relevant files. Key things to check:

- `:root` CSS variables on scalepad.com → `scalepad-design-system.md`
- Product color tokens (`--color-product-*`) → `scalepad-deck-guide.md`
- New resource card illustrations → `scalepad-illustration-guide.md`
- Logo asset URLs (`/scalepad-logo.svg`, `/product-logos/*.svg`) → `scalepad-deck-guide.md`

---

*Maintained by Tulsie Narine · ScalePad Solutions Engineering · Last extracted: June 2026*
