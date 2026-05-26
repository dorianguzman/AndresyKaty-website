# Handover — AndresyKaty Website

## Current State
- **Status:** Section-by-section reference improvements in progress
- **Live file:** `index.html` (single-file, no build)
- **Repo:** https://github.com/dorianguzman/AndresyKaty-website
- **Completed sections:** Hero (1) ✅, Location (2) ✅, Timeline (3) ✅, Accommodation (4) ✅
- **Remaining sections:** FAQ (5), Photos (6), RSVP (7), Gift (8)

### Section 1 — Hero (done)
- Blush `#FCF0F2` background, no dark overlay
- `hero-modified.png` as foreground illustration (transparent bg)
- **Hello Honey** for names (`--font-display`), **The Skinny** for "¡Nos casamos!" + date (`--font-skinny`)
- Date moved into nav (aligned with ES/EN buttons)
- "MORELIA, MX" below illustration in The Skinny
- Scroll indicator at bottom center (bouncing animation)
- ES/EN buttons: The Skinny bold, black border, rose fill on active

### Section 2 — Location (done)
- Venue image fills full section as absolute background layer
- Garnet info panel overlaps bottom with `margin-top: 50vh`, frosted glass: `rgba(122,43,58,0.82)` + `backdrop-filter: blur(8px)`
- Using `jardin-cropped.png` (cropped venue photo, user-provided)
- Venue name: Hello Honey, `clamp(56px, 12vw, 82px)`, white
- Google Maps link: https://maps.app.goo.gl/sxftxGoN9pgtngFC6
- Parallax: `fromTo(-15, 10)` scrub

### Section 3 — Timeline (done)
- Rebuilt: large freeform illustrations (no icon circles), alternating left/right layout
- **Hello Honey** for "timeline" title, **The Skinny** for event labels (Ceremonia, Bienvenida, etc.)
- 3 individual connector SVGs between events: loop (tlc1), S-curve left (tlc2), gentle curve (tlc3) — each draws on scroll via GSAP
- Ceremonia links to Google Maps: https://maps.app.goo.gl/ztnASWmWhxs6tocS8
- TheSkinny accent fix: space after ó in "Celebraci ó n", "Có mo", "Misió n"
- Mobile: alternating left/right layout preserved (no column collapse)

### Section 4 — Accommodation (done)
- **Hello Honey** title, **The Skinny** for hotel names + "Có mo llegar" buttons
- Photo cards: hotel name (uppercase label) → photo (grayscale filter) → button
- Hotel photos: `hotel1-4.jpg` in assets, wired in order
- Country decorations: `mexico-modified.png` (marigolds + cactus) at top border (between timeline and accommodation), `colombia-modified.png` (orchids) at bottom border (between accommodation and FAQ)
- Decorations: 160px, rotated ±15°, z-index: 10, overflow removed from accommodation + FAQ
- Andrés = Colombia, Katia = Mexico

### Open items
- FAQ (5), Photos (6), RSVP (7), Gift (8) still to review
- No deployment set up yet (GitHub Pages or Netlify — TBD)
- Hotel Google Maps links are generic queries — user may want to update with direct links

---

## The Style We Are Building

This is the single most important thing to preserve across every future change.

### Aesthetic Direction
**Boho-romantic, Mexican, hand-illustrated.** The reference is the *Paula y Nerea* website style: editorial flat illustrations, warm earthy palette, handwritten type mixed with clean sans-serif, and festive cultural touches (tacos, orange slices, Talavera tiles, azulejo decorations). Not a template — feels custom-drawn.

Key adjectives: **warm, intimate, slightly playful, artisanal, not corporate.**

### Color Palette

| Token | Hex | Use |
|-------|-----|-----|
| `--garnet` | `#7A2B3A` | Primary brand — buttons, headings, backgrounds |
| `--garnet-dark` | `#5C1F2C` | Hover states, deep accents |
| `--blush` | `#FCF0F2` | Light section backgrounds |
| `--cream` | `#FDF6F0` | Page base, cards, form fields |
| `--rose` | `#D4899A` | Secondary accent — borders, hearts, tags |
| `--gold` | `#C9A84C` | Detail accent — stars, trim, SVG highlights |
| `--orange-soft` | `#E8956D` | Festive accent — taco, orange slice, garland |
| `--text-dark` | `#2D1A1F` | Body text |

**Supporting values (not tokenized):**
- `#8a6070` — muted brownish-rose for secondary/meta text
- `#7a8c45` — sage green for leaf accents in SVGs only
- Shadow: `0 2px 20px rgba(122,43,58,0.08–0.15)` (garnet-tinted, never grey)

**Gradients:**
- Submit button: `linear-gradient(135deg, var(--rose) 0%, var(--garnet) 100%)`
- Hero overlay: `linear-gradient(to bottom, rgba(45,26,31,0.1) 0%, rgba(45,26,31,0.75) 100%)`

### Typography

| Role | Family | CSS Var | Notes |
|------|--------|---------|-------|
| Display / couple names | Hello Honey | `--font-display` | `clamp(72px, 18vw, 110px)`, venue name `clamp(56px, 12vw, 82px)` |
| Handwritten secondary | The Skinny | `--font-skinny` | "¡Nos casamos!", date, "MORELIA MX", scroll indicator |
| Script fallback | Caveat | `--font-script` | Still used for timeline, FAQ, footer titles |
| Body / UI | Nunito | `--font-body` | Labels, body text, buttons |

**Font files:** `assets/fonts/HelloHoney.otf`, `assets/fonts/TheSkinny.otf`, `assets/fonts/TheSkinny-bold.otf`
**Rule:** Hello Honey = big emotional display. The Skinny = casual handwritten secondary. Caveat = remaining script sections. Nunito = everything functional.

### Shape & Spacing Language
- Buttons: `border-radius: 50px` (pill)
- Cards / hotel blocks: `border-radius: 16–20px`
- FAQ items: `border-radius: 14px`
- Inputs: `border-radius: 50px`
- Shadows are always garnet-tinted, never neutral grey

### SVG Illustration Style
All SVGs are inline and hand-crafted to feel drawn. Rules:
- Use only palette colors (garnet, blush, rose, gold, orange-soft, cream, sage green for leaves)
- No photorealistic detail — flat shapes with stroke outlines
- Stroke colors should be a darker version of the fill (e.g., `#C9854A` outlines `#E8B87A` fill)
- Decorative use only — never replace text with SVG text

**Illustrations built:**

| Section | SVG | Description |
|---------|-----|-------------|
| Timeline | Church | Ceremony event marker |
| Timeline | Wedding Car | K&A getaway car |
| Timeline | Wine Glass | Cocktail hour |
| Timeline | Party Stars | Celebración, with music note |
| Accommodation | Azulejo Tile | 4-petal flower tile (80×80) |
| FAQ | Talavera Tiles (×2) | Corner decorations (80×80) |
| Photos | Camera + Polaroid | With heart inside |
| RSVP | Taco | Mexican food decoration |
| RSVP | Orange Slice | Mexican food decoration |
| Gift | Envelope + Bills | Lluvia de sobres |
| Gift | Suitcase + Stickers | Luna de miel |
| RSVP Thanks | Heartbeat Heart | Animated (heartbeat CSS) |
| Footer | Small Heart | Rose, 0.7 opacity |

### Section Architecture (in order)

1. **Nav** — fixed, transparent → solid on scroll; ES/EN language toggle right
2. **Hero** — full viewport; illustrated `hero.jpg` background; dark gradient overlay; Caveat display text
3. **Location** — parallax venue photo (left) + info block (right); garnet background for info
4. **Timeline** — large freeform illustrations; 3 individual connector curves drawn on scroll; GSAP per-connector
5. **Accommodation** — 4 photo cards (grayscale images); country botanicals (Mexico/Colombia) as section border decorations
6. **FAQ** — accordion; Talavera tile corner decorations; CSS max-height toggle
7. **Photo Upload** — simple CTA section with camera/polaroid SVG
8. **RSVP** — form sends WhatsApp to +353 83 072 4617; taco + orange slice decorations
9. **Gift Registry** — 2-card grid: envelope (cash) + suitcase (honeymoon)
10. **Footer** — names + heart + subtle copy

### Animations
- Hero: entrance sequence (announce → names → date), opacity + y translate, staggered
- Location image: parallax `yPercent: 25`, scrub 1
- Timeline path: stroke-dashoffset draw, scrub
- Timeline events: slide in from sides (left events x:-60, right events x:+60)
- `.reveal` class: generic fade + y:40→0 on scroll
- Hotel cards: staggered fade + y:50 (0.15s stagger)
- Gift cards: scale 0.85→1 + fade (0.2s stagger)
- Photos illustration: scale 0.5→1 bounce
- RSVP thanks heart: `heartbeat` CSS keyframe (scale 1→1.15, infinite)

### Responsiveness
- Single breakpoint: `@media (max-width: 600px)`
- Grids collapse to 1 column
- Timeline collapses (events stack)
- Font sizes use `clamp()` throughout

---

## Key Decisions Made

- **Single file** — user explicitly wants HTML/CSS/JS vanilla, no frameworks, no build step
- **GSAP via CDN** — not npm-installed; links to cdnjs 3.12.5
- **Hero = flat illustration** (`hero.jpg`) — not the couple photo (`pic.jpeg`). User provided the illustrated version. This is the intended hero.
- **image3.jpeg** — placeholder venue photo. User will provide a real one. Replace `assets/image3.jpeg` when provided.
- **WhatsApp RSVP** — number is +353 83 072 4617 (`wa.me/353830724617`). Opens in new tab with pre-filled Spanish message.
- **Venue name** — Jardín Santa Sofía, Morelia, México
- **Date** — 20/03/2027

---

## User Preferences & Corrections
- Do not use frameworks — vanilla only
- SVG illustrations built inline, not as files
- Inspired by "Paula y Nerea" illustrated wedding site style
- RSVP sends to WhatsApp, not email or a backend
- Reference images go in `reference/` folder, not root
- Active assets go in `assets/` folder

---

## Gotchas & Pitfalls
- `image3.jpeg` is the venue photo used in the location section — do not move it to reference
- `hero.jpg` is the illustration (flat art), not the photo. `pic.jpeg` in reference is the actual photo and is no longer used.
- All colors must come from CSS custom properties. Never hardcode hex in component HTML.
- i18n: every user-facing string needs both ES and EN entries in the translations object in `index.html`

---

## Files That Matter

| File | What it is |
|------|-----------|
| `index.html` | Entire site — HTML + CSS + JS in one file |
| `assets/hero.jpg` | Illustrated hero — flat art of Katia y Andrés with giant ring |
| `assets/jardin.jpg` | Venue exterior photo — Jardín Santa Sofía, Morelia |
| `assets/jardin-cropped.png` | Cropped venue photo used in location section |
| `assets/hotel1-4.jpg` | Hotel photos for accommodation cards |
| `assets/mexico-modified.png` | Marigolds + cactus illustration (transparent bg) — Katia/Mexico deco |
| `assets/colombia-modified.png` | Orchids illustration (transparent bg) — Andrés/Colombia deco |
| `reference/pic.jpeg` | Original couple photo (not used on site, kept for reference) |
| `tasks/handover.md` | This file — style guide + session state |

---

## Open Questions
- Deployment: GitHub Pages or Netlify? (ask user)
- Final venue photo: user will provide — drop in `assets/`, likely rename to `venue.jpg`
- Any additional sections needed? (Dress code, transport info, etc.)
- Google Maps link for venue: currently a placeholder `#` — needs real URL
