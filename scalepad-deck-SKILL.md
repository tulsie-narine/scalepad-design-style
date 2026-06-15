---
name: scalepad-deck
description: Build any ScalePad-branded slide deck (.pptx) — sales pitch, all-hands, board update, product launch, kickoff, QBR, exec readout, demo deck. Ships a bold on-brand layout library (cover, section, agenda, content, two-column, three-up, stat hero, stat grid, quote, image, bullets, comparison, logo wall, closing) plus dark and light themes that share layouts. Use any time the user asks for a ScalePad deck, slides, or presentation — including casual phrasing like "build me slides", "pitch deck", "launch deck", "all-hands deck", or "make a presentation". Defer to scalepad-roadmap-deck only when the user specifically wants a roadmap deck pulled from Jira Product Discovery.
---

# ScalePad Deck Builder

This skill turns a structured JSON spec into a polished, ScalePad-branded `.pptx`. It
ships a bold visual language (oversized type, full-bleed accent panels, color-coded
section moments) and a layout library that handles the shapes most decks need —
sales pitch, all-hands, product launch, board readout. It supports two themes that
share the same layout library: **dark** (Dark Matter canvas, white type) and **light**
(white canvas, Dark Matter type). The deck can mix themes per slide if needed.

The skill is **independent** from `scalepad-roadmap-deck` — that one stays the
specialized workflow for pulling roadmap data from Jira Product Discovery. This skill
is the general-purpose deck builder.

## When to use

Reach for this any time a user asks for a ScalePad slide deck, presentation, or
".pptx" — even casually:

- "Build me a sales pitch deck for Quoter"
- "Put together an all-hands deck for next week"
- "Make a product launch deck for the new ControlMap integration"
- "I need slides for the board on Q3 results"
- "Slide deck explaining the new pricing"
- "Pitch deck for prospects, dark theme please"

If the user explicitly says they want the roadmap deck pulled from Jira Discovery
projects, defer to `scalepad-roadmap-deck` instead. Anything else, use this skill.

## How it works

You collaborate with the user to fill in a deck spec (a JSON file with deck-level
metadata and a `slides` array), then run:

```bash
node scripts/build_deck.js <spec.json> <out.pptx>
```

The script renders each slide using the right layout from the bundled library,
applies the chosen theme, and post-processes the .pptx zip to embed Inter directly
so the deck renders correctly on machines without Inter installed locally.

## What ships with this skill

```
scalepad-deck/
├── SKILL.md                       # this file
├── scripts/
│   ├── build_deck.js              # renders the .pptx from a spec
│   ├── package.json               # pptxgenjs dependency
│   └── node_modules/              # auto-installed dependencies
├── references/
│   ├── design_system.md           # the bold-color-block aesthetic, type/spacing scale
│   ├── layouts.md                 # every layout, its fields, and when to use it
│   ├── spec_schema.md             # full deck/slide JSON shape
│   └── workflow.md                # how to take a request → spec → .pptx
├── examples/
│   ├── sales_pitch_dark.json      # Quoter-themed sales pitch (dark)
│   ├── all_hands_light.json       # Internal all-hands (light)
│   └── product_launch_dark.json   # ControlMap launch (dark)
└── assets/
    ├── fonts/                     # Inter (Regular, Bold, Italic, BoldItalic)
    ├── logos/                     # ScalePad master + product logos (curated subset)
    └── palette.json               # Frontify-verified palette (mirrored from brand skill)
```

## Workflow

### Step 1 — Confirm the brief

Use `AskUserQuestion` to lock the basics before drafting:

- **Audience** — Customers / prospects / partners / internal / board. Affects tone
  and how much technical detail belongs in the deck.
- **Theme** — Dark (recommended for sales/launch — feels premium, high-contrast)
  or light (recommended for internal all-hands, board readouts — easier to project
  in a bright room, more text-friendly).
- **Primary product accent** — `ATMOSPHERE` (Lifecycle Manager), `RADAR` (Backup
  Radar), `GALAXY` (ControlMap), `COSMOS` (Quoter), `NEBULA` (Cognition360),
  `MARTIAN` (Lifecycle Insights). For decks that span the whole suite, default to
  `ATMOSPHERE` — it's the suite-level color in the rest of ScalePad GTM.
- **Length** — typical decks land at 8–14 slides for sales pitch, 10–18 for
  all-hands, 6–10 for launch announcements.

If the request already includes content (an outline, an existing doc, talking
points), pull as much as you can from there before asking the user to fill gaps.

### Step 2 — Draft the spec

Write a JSON spec file with two top-level keys: `deck` (metadata) and `slides` (an
ordered array). The full schema is in `references/spec_schema.md`. Keep slides
short — one idea per slide. The bold visual language **does not work** if you
cram a slide; it relies on negative space and oversized type doing the work.

Save the spec to `/tmp/<deck-name>.json` (or anywhere). You'll regenerate it as
the deck evolves, so picking a stable path makes iteration painless.

### Step 3 — Render the deck

```bash
cd <skill_path>/scripts
# first time only: npm install   (pptxgenjs is the only dependency)
node build_deck.js /tmp/<deck-name>.json mnt/outputs/<deck-name>.pptx
```

The script logs warnings for unknown color tokens and unknown layout names — read
the output. Layout names are listed in `references/layouts.md`.

### Step 4 — Visual QA (required)

Convert the deck to images and have a subagent inspect, exactly as the `pptx`
skill recommends. Don't skip this — the first render usually has 1–3 user-visible
defects (a long title that wraps unexpectedly, a stat that needs a smaller font,
an image side that needed flipping).

```bash
python ~/.claude/skills/pptx/scripts/office/soffice.py --headless --convert-to pdf mnt/outputs/<deck-name>.pptx
rm -f /tmp/slide-*.jpg
pdftoppm -jpeg -r 120 mnt/outputs/<deck-name>.pdf /tmp/slide
ls -1 "$PWD"/slide-*.jpg
```

Spawn a `general-purpose` subagent with the slide paths and the standard QA prompt
from the `pptx` skill. Fix any user-visible defects (overlap, overflow, low
contrast, leftover placeholder text), re-render, and re-verify only the affected
slides. Stop after one fix-and-verify cycle unless something genuinely
user-visible remains.

### Step 5 — Deliver

Drop the final `.pptx` into `mnt/outputs/` and share via a `computer://` link.
Tell the user that to get a Google Slides version they can drop the file into
Drive → right-click → *Open with Google Slides*. The deck has Inter embedded so
it renders correctly in PowerPoint, Keynote, and Slides without any local font
install.

## Themes

The deck has two themes — **dark** and **light** — and they share the same layout
library. Pick one at the deck level (`deck.theme`) and override per-slide
(`slides[].theme`) when needed. A common pattern is dark deck with a couple of
light "data table" or "comparison" slides, or vice versa.

| Token       | Dark theme           | Light theme          |
|-------------|----------------------|----------------------|
| Background  | Dark Matter (#0A1C2B)| White (#FFFFFF)      |
| Surface alt | Dark Matter Deep     | Oxygen (#F5F5F5)     |
| Body text   | White                | Dark Matter          |
| Muted text  | Starlight (#B8BCC0)  | Moon Rock (#7E8081)  |
| Divider     | Deep navy hairline   | Pale gray hairline   |
| Accent      | Product accent       | Product accent       |

The accent color comes from the deck's chosen product (e.g., `ATMOSPHERE` for an
LM-focused deck, `COSMOS` for a Quoter-focused one). Section divider slides invert
the canvas: the section slide fills the entire frame with the accent and uses
white (or Dark Matter, depending on contrast) for type. This gives the deck a
strong rhythm — content slides → big accent moment → content slides.

## Brand alignment

This skill consumes the same brand source-of-truth as `scalepad-brand-guidelines`:

- Palette tokens are the seven primary plus five secondary from
  `assets/palette.json` (mirrored from the brand skill — refresh together).
- Typography is **Inter** (the effective ScalePad type, per the brand skill's
  Roboto-vs-Inter override). Embedded directly into every .pptx.
- Logos come from `assets/logos/` (curated subset of the brand skill's library).
  The script auto-picks the master logo variant by theme — white on dark, black
  on light — and never recolors a logo SVG. The fills are brand-locked.
- Casing follows Frontify rules: **headlines** are sentence case with no end
  punctuation; **subheads** are sentence case with end punctuation; **CTAs** are
  title case with no end punctuation; **eyebrows** can be caps for graphic effect.

If you produce something that needs strict Frontify compliance (legacy print
templates, partner co-brand kits), tell the user — this skill defaults to Inter,
and switching to Roboto would require a different assets/fonts bundle.

## Common pitfalls

1. **Don't cram slides.** The visual language relies on oversized type and
   generous whitespace. If you find yourself fitting more than ~6 bullets or
   3 cards on a single slide, split it across two slides — it'll look better and
   communicate better.
2. **Don't pick raw hex colors.** The script accepts brand tokens
   (`ATMOSPHERE`, `COSMOS`, etc.) and resolves them to the canonical hex. Raw
   hex values work but trigger a warning, since they bypass brand drift checks.
3. **Don't apply random per-slide accents** for decoration. Each slide inherits
   the deck-level accent unless there's a real reason to change it (e.g., a
   product-comparison slide where each panel needs its product color).
4. **Don't over-use the section layout.** It's the deck's exclamation mark —
   one every 4–6 slides at most. Past that, it stops reading as a section break
   and starts reading as a hairshirt.
5. **Don't forget headlines are sentence case.** "Win bigger deals, faster" not
   "Win Bigger Deals, Faster". The brand check script in
   `scalepad-brand-guidelines` won't flag casing, so reviewers might miss it.
6. **Don't embed PNGs of slide content.** If the user supplies a screenshot,
   use the `image` layout to half-bleed it — don't paste it into a `content`
   slide as a tiny inline image.

## Reference files

Read these before drafting a complex deck:

- `references/design_system.md` — the why behind the type scale, color blocking,
  whitespace rhythm. Skim it once; it'll save you from making timid choices.
- `references/layouts.md` — every layout, its required and optional fields, when
  it shines, when it doesn't. Reach for this whenever you're unsure which layout
  fits a piece of content.
- `references/spec_schema.md` — the JSON shape. Use as a quick reference when
  building specs.
- `references/workflow.md` — the longer "how to take an ambiguous request and
  turn it into a spec" walkthrough, with worked examples.

Examples in `examples/` are runnable. To preview what the skill produces:

```bash
node scripts/build_deck.js examples/sales_pitch_dark.json /tmp/sales_pitch_dark.pptx
node scripts/build_deck.js examples/all_hands_light.json  /tmp/all_hands_light.pptx
node scripts/build_deck.js examples/product_launch_dark.json /tmp/product_launch_dark.pptx
```

## Test it

A quick smoke test prompt for this skill:

> "Build me a 10-slide sales pitch deck for Backup Radar. Dark theme. Audience is
> MSP owners who haven't bought a backup monitoring tool before."

A correct response: confirms audience/theme/length via AskUserQuestion, drafts a
JSON spec mixing cover, section, content, stat_hero, three_up, quote, comparison,
and closing layouts, runs `build_deck.js`, does a visual QA pass via subagent,
and delivers the .pptx with a `computer://` link. The deck reads as ScalePad
on every slide (Dark Matter canvas, RADAR accent, Inter throughout, sentence-case
headlines), and Inter is actually embedded in the file (verify with `unzip -l
out.pptx | grep ttf`).

## Live design reference (GitHub)

The canonical brand tokens, product colors, logo URLs, hero gradients, layout patterns, and copy guidelines are maintained in the ScalePad design style repo. Fetch these at the start of any complex deck build:

```
# Core design system — colors, typography, CSS tokens
https://raw.githubusercontent.com/tulsie-narine/scalepad-design-style/main/scalepad-design-system.md

# Deck-specific guide — logos, product tokens, slide layouts, copy patterns
https://raw.githubusercontent.com/tulsie-narine/scalepad-design-style/main/scalepad-deck-guide.md
```

### Key additions in the deck guide not in this SKILL.md

- **Logo asset URLs** — master logo, all five product lockups (color + white variants), product icons, compliance badges — all served as SVGs from scalepad.com
- **Product color tokens** — exact CSS vars and hex values extracted live from scalepad.com:
  - `--color-product-lm` → `#4ba384` (Lifecycle Manager)
  - `--color-product-cm` → `#693568` (ControlMap)
  - `--color-product-qt` → `#b71e74` (Quoter)
  - `--color-product-br` → `#216092` (Backup Radar)
  - `--color-product-c360` → `#cf304c` (Cognition360)
  - `--color-platform-accent` → `#8f96ff` (Platform/API slides)
- **Exact hero gradients** per product (45deg dark-to-light, with white radial overlay)
- **Seven slide layout patterns** with field specs mapped from the website
- **Product taglines** (verbatim, for use on product-specific slides)
- **Illustration style guide** (flat line-art, gold/teal fills, geometric accents)
- **Standard 10-slide sales pitch sequence**

