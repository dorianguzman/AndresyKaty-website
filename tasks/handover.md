## Current State
- **Status:** All 8 sections complete — font system unified, botanical decorations wired, RSVP + Gift functional
- **Live file:** `index.html` (single-file, no build)
- **Repo:** https://github.com/dorianguzman/AndresyKaty-website
- **Git:** 10 commits ahead of origin/main — NOT pushed yet
- **All sections done:** Hero (1) ✅, Location (2) ✅, Timeline (3) ✅, Accommodation (4) ✅, FAQ (5) ✅, Photos (6) ✅, RSVP (7) ✅, Gift (8) ✅

---

## Font System (LOCKED — apply to all future sections)

| Role | Font | CSS Var | Size |
|------|------|---------|------|
| Section titles | HelloHoney | `--font-display` | `clamp(48px, 10vw, 76px)` |
| Card titles | HelloHoney | `--font-display` | `28px` |
| Secondary / body | TheSkinny | `--font-skinny` | `16–20px` |
| Body (functional) | Nunito | `--font-body` | labels, inputs |

**TheSkinny spacing rules (CRITICAL — apply to ALL --font-skinny text):**
1. Always apply `letter-spacing: 0.06em`
2. Space after `¿` and `¡` openers
3. Space after every accented letter (á, é, í, ó, ú, ñ) when immediately followed by another letter
4. Space after `/`
5. Space after `'`
6. NEVER apply these rules to --font-display (HelloHoney) or --font-body (Nunito)

---

## Botanical Decoration Pattern (LOCKED)

Section borders use absolutely-positioned PNG illustrations (transparent bg, 160px wide):
- `translateY(50%) rotate(-15deg)` → peeks UP from bottom of section into next
- `translateY(-50%) rotate(15deg)` → peeks DOWN from top of section into previous
- `left: 50%; transform: translateX(-50%)` → centered
- `z-index: 10`, `pointer-events: none`
- Parent section needs `position: relative` (NOT `overflow: hidden`)

**Current border decorations:**
| Position | Asset | Class |
|----------|-------|-------|
| Accommodation top-center | `mexico-modified.png` | `accommodation-deco.right` (centered) |
| Accommodation bottom-left | `colombia-modified.png` | `accommodation-deco.left` |
| FAQ top-right | `faq-mexico.png` (butterfly+hummingbird) | `faq-deco.right` |
| FAQ bottom-center | `faq-colombia.png` (toucan+coffee) | `faq-deco.left` (centered) |
| Photos bottom-center | `rsvp-colombia-modified.png` (coffee+arepa) | `photos-border-deco` |
| RSVP bottom-center | `rsvp-mexico-modified.png` (taco+tequila) | `rsvp-border-deco` |

**Generated assets (cloudflare-flux + PIL bg removal):**
- `faq-mexico.png` / `faq-mexico-modified.png` — monarch butterfly + hummingbird
- `faq-colombia.png` / `faq-colombia-modified.png` — toucan + coffee branch
- `rsvp-mexico.png` / `rsvp-mexico-modified.png` — taco + tequila
- `rsvp-colombia.png` / `rsvp-colombia-modified.png` — coffee + arepa

---

## Section Notes

### Section 1 — Hero ✅
- `hero-modified.png` illustration, blush background
- HelloHoney for names, TheSkinny for "¡ Nos casamos!" + date

### Section 2 — Location ✅
- `jardin-cropped.png` parallax (`fromTo(-15, 10)`)
- Frosted glass garnet panel, Google Maps link wired

### Section 3 — Timeline ✅
- 4 events with inline SVG illustrations, alternating L/R
- 3 SVG connector paths drawn on scroll via GSAP
- TheSkinny spacing applied: `Celebració n`, `Có mo`, etc.

### Section 4 — Accommodation ✅
- 4 hotel cards (grayscale photos), TheSkinny hotel names + buttons
- `mexico-modified.png` centered at top, `colombia-modified.png` at bottom-left

### Section 5 — FAQ ✅
- HelloHoney title `clamp(48px, 10vw, 76px)`
- TheSkinny questions (20px) + answers (16px) with full spacing rules
- `faq-mexico.png` top-right, `faq-colombia.png` bottom-center
- Accordion: single-open, `+` indicator fixed (`.faq-question span:first-child` scoped selector)

### Section 6 — Photos ✅
- HelloHoney title, TheSkinny body (20px)
- Camera+polaroid SVG — `reveal` class removed (was causing flicker with dedicated GSAP animation)
- Upload button → Knipsmig: https://knipsmig.com/pgalYgcS (placeholder — replace with real link before wedding)
- `rsvp-colombia-modified.png` (coffee+arepa) centered at bottom border

### Section 7 — RSVP ✅
- Form: TheSkinny on all labels, inputs, toggle, submit button
- WhatsApp: +353 83 072 4617, language-aware message (ES/EN)
  - ES: "Nos vemos en la boda — Katia y Andrés"
  - EN: "See you at the wedding! — Katia & Andrés"
- Default: plus-one = No (guest field hidden)
- Deadline: `01/ 01/ 2027` numeric format both languages
- `rsvp-mexico-modified.png` (taco+tequila) centered at bottom border

### Section 8 — Gift ✅
- Garnet background, 2 cards (envelope SVG + suitcase SVG)
- HelloHoney titles, TheSkinny body/lead
- **Transfer modal on Luna de miel card:**
  - "Contribuir" button → modal with MX / EU tabs
  - MX: CLABE placeholder `0000 0000 0000 0000 0000` + copy button (NEEDS REAL CLABE)
  - EU: Revolut `@username` + copy button + "Abrir Revolut" link (NEEDS REAL REVOLUT)
  - Copy button turns green with ✓ for 2s
  - Closes on backdrop click or ×

---

## OG Image (Social Sharing)

- `assets/og-export.html` — editable 1200×630 template (HelloHoney + TheSkinny, same brand system)
- `assets/og-image.png` — exported PNG, regenerate with:
  ```
  /Applications/Google\ Chrome.app/Contents/MacOS/Google\ Chrome --headless --screenshot=assets/og-image.png --window-size=1200,630 --hide-scrollbars "file:///$(pwd)/assets/og-export.html"
  ```
- Layout: text left, hero illustration absolutely positioned right (names overlap image), butterfly+hummingbird top-left, toucan+coffee bottom-left
- Meta tags added to `index.html` — replace `PLACEHOLDER_DOMAIN` with real URL after deploy

---

## Open Items

### Before wedding:
- [ ] Replace `PLACEHOLDER_DOMAIN` in `index.html` OG/Twitter meta tags with real deployed URL
- [ ] Replace Knipsmig link with real upload event link (Photos section)
- [ ] Fill in real MX CLABE number in transfer modal HTML (`0000 0000 0000 0000 0000`)
- [ ] Fill in real Revolut username (`@username`) and link (`https://revolut.me/username`)
- [ ] Set up deployment (GitHub Pages or Netlify — TBD)

### Remaining design work:
- [ ] Footer review — fonts not yet matched
- [ ] Nav review — fonts not yet checked
- [ ] Gift section bottom border decoration (nothing peeking into footer yet)
- [ ] Final venue photo — user will provide, drop in `assets/`
- [ ] Hotel Google Maps links — currently generic, user may want direct links

---

## Files That Matter

| File | What it is |
|------|-----------|
| `index.html` | Entire site — HTML + CSS + JS |
| `assets/hero-modified.png` | Illustrated hero (transparent bg) |
| `assets/jardin-cropped.png` | Venue photo for location section |
| `assets/hotel1-4.jpg` | Hotel photos (accommodation) |
| `assets/mexico-modified.png` | Marigolds + cactus (Katia/Mexico) |
| `assets/colombia-modified.png` | Orchids (Andrés/Colombia) |
| `assets/faq-mexico-modified.png` | Butterfly + hummingbird (FAQ) |
| `assets/faq-colombia-modified.png` | Toucan + coffee (FAQ) |
| `assets/rsvp-mexico-modified.png` | Taco + tequila (Photos→RSVP border) |
| `assets/rsvp-colombia-modified.png` | Coffee + arepa (RSVP→Gift border) |
| `assets/og-export.html` | Editable OG image template (1200×630) |
| `assets/og-image.png` | Exported OG image for social sharing |
| `tasks/handover.md` | This file |
| `tasks/context.md` | Corrections log + TheSkinny rules |

---

## Key Decisions
- Single vanilla HTML file, no frameworks, no build step
- GSAP via CDN (cdnjs 3.12.5)
- WhatsApp RSVP — opens wa.me link with pre-filled message, language-aware
- Botanical images generated via cloudflare-flux, bg removed with PIL
- All botanical images: generated + `-modified` (transparent bg) versions kept
- TheSkinny spacing rules apply to all --font-skinny text — logged in context.md
