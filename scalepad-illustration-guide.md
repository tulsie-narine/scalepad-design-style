# ScalePad Illustration Style Guide

> Extracted by visual analysis of scalepad.com resource illustrations — June 2026  
> Companion to `scalepad-design-system.md` and `scalepad-deck-guide.md`  
> Use this when generating, prompting, or directing AI image tools, SVG illustration work, or briefing designers.

---

## Overview

ScalePad uses a consistent illustration language across all resource cards, playbook covers, learning series thumbnails, and marketing materials. It is **not** a generic stock illustration style — it has specific, repeatable characteristics that make it immediately recognizable as ScalePad.

The style sits at the intersection of **editorial comic art** and **flat design** — expressive characters with visible line weights and hand-drawn texture, combined with flat gold fills and a limited brand palette. Think: *Mailchimp meets classic editorial illustration, restrained to two accent colors.*

---

## The two illustration modes

ScalePad uses two distinct visual modes, never mixed within the same composition:

### Mode 1 — Character illustration
Human figures in action poses, surrounded by relevant objects and symbols. Used for learning series, playbooks, and conceptual content.

### Mode 2 — Abstract / geometric
No characters. Pure shapes, arrows, grids, meshes, or symbolic objects. Used for reports, data-heavy content, and technical subjects.

---

## Mode 1: Character illustration system

### Body construction

Characters are drawn with a **simplified comic anatomy**:

- **Head:** large relative to the body (approx 1:5 head-to-body ratio, slightly cartoonish)
- **Face:** minimal — two dot eyes, a small curved smile or neutral expression, one eyebrow raised for personality
- **Hair:** filled solid Gold (`#eba900`) — this is the single most distinctive trait. All characters have gold hair. No exceptions observed.
- **Skin:** left as the paper/background color — faces and hands are the outline only, no fill color. The background shows through.
- **Body:** white or very light gray fill with dark navy outline strokes
- **Clothing:** white shirt/jacket base, dark navy/black trousers or details, occasional accessory in gold (hat, badge, plume)
- **Outline weight:** 2–3px equivalent stroke, slightly irregular — gives the impression of hand-drawn even when vector

### Pose vocabulary

Characters are always in **dynamic action poses** — never standing still or in a neutral pose:

| Pose | Used for |
|------|----------|
| Striding forward confidently | Sales, growth, leadership content |
| One foot up on an object | Mastery, overcoming obstacles (the hiker pose) |
| Pointing at something off-frame | Directing attention, discovery |
| Leaning/peering at a screen | Analysis, metrics, BI content |
| Combat stance (sword raised) | Security, compliance, defending against threats |
| Looking up with hand on chin | Strategy, thinking, planning content |
| Arms raised in achievement | Success, completion, celebration |

### Accessories and props

Props reinforce the narrative. Every character illustration includes 2–4 props:

**Character accessories (gold-filled):**
- Explorer/hiker hat with brim
- Knight's visor helmet with gold plume
- Backpack or satchel
- Sword and shield (shield shows checkmark)
- Tie or business accessory

**Floating symbolic objects around the character:**
- Security shield with checkmark (`#eba900` fill, navy outline)
- Warning triangle with `!` symbol
- Lock/padlock (closed = secure, broken = threat)
- Arrows pointing up (growth, progress)
- Progress arc/gauge/speedometer
- Document/certificate with skull (threat document)
- Cloud shapes
- Gear/cog shapes (processes, automation)
- Laptop/screen (product context)
- Sunglasses (MVP, success content — these are solid gold 3D objects)

### Symbolic object construction

Floating objects follow the same rules as characters:
- **Outline:** 2–3px dark navy stroke
- **Fill:** Gold (`#eba900`) for accent objects, white for secondary objects, dark navy for threat/danger objects
- **No gradients** on symbolic objects — flat fills only
- **Slight rotation** — objects are never perfectly upright, usually 5–15° tilt for dynamism

### Line quality

The outline style is semi-irregular — not perfectly smooth bezier curves:
- **Slight wobble/variation** in stroke width along a path (thicker at corners, thinner mid-stroke)
- **Cross-hatching** used sparingly inside dark fills (shoes, hair, dark clothing) to add texture
- **Sketch lines** for speed/motion on arrows (parallel lines alongside the arrow shaft)
- This gives vector art a hand-drawn editorial feel without being sloppy

### Color rules for characters

| Element | Color | Notes |
|---------|-------|-------|
| Hair | `#eba900` (Gold) | Always. The single unifying brand trait. |
| Skin / face | Transparent (background shows through) | Outline only, no fill |
| Shirt / jacket | `#ffffff` or `#f0f0f0` | Near-white, slight warm tint |
| Trousers / dark clothing | `#1a1a2e` or `#0a1c2b` | Near-navy, not pure black |
| Outfit accent detail | `#eba900` or product accent | Tie, badge, patch |
| Hero prop fill | `#eba900` | Shield, arrows, hat, key object |
| Secondary prop fill | `#ffffff` | Documents, clouds |
| Threat/danger prop | `#1a1a2e` or `#3d2060` | Locks, skulls |
| Outline stroke | `#1a1a2e` | Consistent dark navy, not black |

---

## Mode 2: Abstract / geometric illustration system

### Type A — Floating symbol compositions

Isolated objects from the character vocabulary (arrows, shields, gears, locks) arranged compositionally without a character. Used when the concept is an object rather than a person.

**Rules:**
- Objects at varying scales (largest ~60% frame height, smallest ~15%)
- Slight rotation on each — no element is perfectly upright
- 2–4 objects maximum per composition
- Background texture: large faded version of primary object at ~10–15% opacity

**Seen on:** Arrow growth chart (Masterclass), padlock laptop (Boot Camp), warning document

### Type B — 3D mesh / geodesic shapes

Abstract 3D-looking shapes built from a grid of rounded squares connected at nodes. Appears on infrastructure, networking, and technical content.

**Construction:**
- Shape silhouette: organic blob or shield form
- Surface treatment: regular grid of rounded squares (~12–16 squares visible)
- Grid lines: `rgba(255,255,255,0.6)` or dark on light backgrounds
- Corner nodes: small filled circles at each grid intersection
- Fill: very dark navy `#0a1c2b` or near-black
- No gold accents on this style — monochromatic

**Seen on:** Infrastructure Protection MSA kit card (the dark folded-paper/shield shape)

### Type C — Large typographic/object 3D renders

Oversized 3D-rendered text or objects, heavily stylized. Dark purple/navy palette with specular lighting lines.

**Seen on:** 2026 MSP Trends Report (the "2026" 3D number sculpture), white line contour style

---

## Background system

Illustration backgrounds are always a **solid product accent color** — never a photograph, never gradient-heavy (slight vignette OK). The illustration floats on top.

| Background color | Used with |
|-----------------|-----------|
| ControlMap purple `#3d1a4a` | Security, compliance, vCISO illustrations |
| Lifecycle Manager dark teal `#0d2e28` | Growth, customer success illustrations |
| Navy `#0a1c2b` / `#0d1b2a` | Data, infrastructure, technical illustrations |
| Deep forest green `#1a3a2a` | Success, MSP achievement illustrations |

**Background texture (optional):** a very large, low-opacity version of the primary symbolic object (lock, shield, gear) repeated at ~8–12% opacity as a watermark behind the main illustration. This adds depth without competing with the foreground.

---

## Icon system (UI icons, not illustrations)

For product UI icons, feature icons, and slide deck icons, ScalePad uses a **Tabler-compatible outline icon style**:

- **Style:** outline only, no fill, 2px stroke
- **Corner radius:** 3–4px on rounded shapes
- **Size grid:** 24×24px base, 2px padding inside
- **Color on dark backgrounds:** white or product accent
- **Color on light backgrounds:** `#132435` (foreground) or product accent
- **Never use filled/solid icon variants on the same slide as outline icons**

The product app icons (Lifecycle Manager, ControlMap, etc.) are a special case — rounded-square containers with a white symbol inside on a gradient background matching the product color. These are not the same as UI icons and should never be used as decorative elements at small sizes.

---

## AI image generation prompts

Use these prompt formulas when generating ScalePad-style illustrations with AI tools (Midjourney, DALL-E, Firefly, Stable Diffusion):

### Character illustration prompt template

```
Flat vector illustration, editorial comic style, 
[character description in action pose], 
gold hair, white clothing with navy/dark trousers, 
[2-3 floating symbolic objects in scene], 
[product accent color] solid background, 
limited color palette: gold #eba900, white, dark navy #0a1c2b,
2-3px dark outline stroke, slight hand-drawn quality, 
no gradients, no photorealism, no shading,
inspired by Mailchimp illustration style,
clean negative space, centered composition
```

### Example prompts by theme

**Security / compliance (ControlMap):**
```
Flat vector illustration, editorial comic style,
business person in knight armor mid-stride, gold hair, 
white suit jacket, dark trousers, holding a sword and shield with checkmark,
floating warning triangle and document with skull nearby,
deep purple #3d1a4a solid background,
gold #eba900, white, dark navy color palette,
2px dark outline stroke, slight hand-drawn quality,
no gradients, no photorealism
```

**Growth / success (Lifecycle Manager):**
```
Flat vector illustration, editorial comic style,
confident explorer character with one foot raised on a rock, gold hair,
wearing explorer hat, backpack, white jacket,
three gold upward arrows floating nearby, security checkmark shield,
dark teal #0d2e28 solid background,
gold #eba900, white, dark navy color palette,
2px outline stroke, hand-drawn editorial feel,
no gradients, no photorealism
```

**Data / metrics (Cognition360):**
```
Flat vector illustration, editorial comic style,
person leaning thoughtfully on desk with hand on chin, gold hair,
white shirt, looking at a laptop showing a speedometer gauge,
laptop frame in gold, speedometer needle in gold,
dark navy #0a1c2b solid background,
gold #eba900, white, dark navy palette,
2px outline stroke, minimal face detail,
no gradients, no photorealism
```

**Abstract growth arrows (no character):**
```
Flat vector illustration, abstract composition,
three gold upward arrows of varying heights, 
tallest in center, slight sketch texture lines on arrow shafts,
faded circular gear shape in background at 10% opacity,
dark navy #0d1b2a background,
gold #eba900 primary color, dark navy outlines,
no characters, no gradients, bold graphic style
```

---

## SVG drawing instructions

When generating SVG illustrations programmatically (for slides, PDFs, or web use):

### Stroke settings
```svg
stroke="#1a1a2e"         <!-- dark navy, not pure black -->
stroke-width="2.5"       <!-- standard outline weight -->
stroke-linecap="round"   <!-- rounded ends on all strokes -->
stroke-linejoin="round"  <!-- rounded joins for softer feel -->
fill="none"              <!-- default for outline paths -->
```

### Gold fill (primary accent)
```svg
fill="#eba900"
stroke="#1a1a2e"
stroke-width="2"
```

### White element with outline
```svg
fill="#ffffff"
stroke="#1a1a2e"
stroke-width="2"
```

### Background container
```svg
<rect width="100%" height="100%" fill="#3d1a4a"/>  <!-- ControlMap -->
<rect width="100%" height="100%" fill="#0d2e28"/>  <!-- Lifecycle Manager -->
<rect width="100%" height="100%" fill="#0a1c2b"/>  <!-- Navy/dark -->
```

### Watermark background object
```svg
<g opacity="0.10" transform="translate(x,y) scale(1.8)">
  <!-- repeat primary symbol path here -->
</g>
```

### Sketch/motion lines on arrows
```svg
<!-- Add these parallel lines alongside arrow shafts for hand-drawn feel -->
<line x1="x" y1="y" x2="x2" y2="y2" stroke="#1a1a2e" stroke-width="1.5" stroke-dasharray="4 3"/>
```

---

## Do / Don't

| Do | Don't |
|----|-------|
| Gold hair on every character | Brunette, black, or red hair |
| Outline-only faces (transparent skin) | Filled/colored skin |
| Dynamic action poses | Standing still, portrait-mode characters |
| 2–3 gold accent objects floating near character | More than 4 objects (gets cluttered) |
| Solid product color background | Gradient-heavy or photo backgrounds |
| Dark navy outlines throughout | Black (`#000000`) outlines |
| Slight tilt on every prop (5–15°) | Perfectly upright/horizontal props |
| White clothing base | Colorful clothing |
| Limited palette: gold + white + navy | Adding green, red, blue fills to characters |
| Background watermark at 8–12% opacity | No watermark (feels flat) |
| Consistent 2–3px stroke weight | Mixed thick/thin strokes without purpose |
| Semi-irregular stroke for hand-drawn feel | Perfectly smooth bezier curves throughout |

---

## When to use illustrations vs other visuals

| Content type | Use |
|-------------|-----|
| Conceptual / metaphorical ("security journey") | Character illustration |
| Data / metrics content | Abstract arrows or 3D render |
| Technical / infrastructure content | Geometric mesh (Mode 2B) |
| Product feature explanation | Product screenshot in white card |
| Social proof / customer story | Photo with product UI overlay |
| Cover slides (sales deck) | Product hero gradient + watermark icon (no illustration needed) |
| Section divider slides | Product gradient + large product icon at 10% opacity |
| Quote slides | Simple background, no illustration |

---

## Quick reference: illustration palette

```css
/* Primary fills */
--ill-gold:        #eba900;   /* hair, shields, arrows, key props */
--ill-white:       #ffffff;   /* clothing, secondary props, face areas */
--ill-navy:        #0a1c2b;   /* outlines, trousers, dark details */

/* Backgrounds */
--ill-bg-purple:   #3d1a4a;   /* ControlMap content */
--ill-bg-teal:     #0d2e28;   /* Lifecycle Manager content */
--ill-bg-navy:     #0a1c2b;   /* General / Backup Radar content */
--ill-bg-dark-teal:#0d1b2e;   /* ScalePad Masterclass / general dark */

/* Stroke */
--ill-stroke:      #1a1a2e;   /* all outlines — dark navy, not black */
--ill-stroke-w:    2.5px;     /* standard stroke width */
```

---

*Last updated: June 2026 · Source: visual analysis of scalepad.com resource illustrations*  
*Companion files: `scalepad-design-system.md` · `scalepad-deck-guide.md`*
