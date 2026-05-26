# AndresyKaty Website — Claude Code Instructions

> First: read `tasks/handover.md`, `tasks/plan.md`, and `tasks/context.md`

## What This Is
Single-file wedding website for Katia y Andrés (20/03/2027, Morelia, México).
Boho illustrated style, fully responsive, bilingual ES/EN, GSAP animations, RSVP via WhatsApp.

## Tech Stack
- Pure HTML/CSS/JS — single file `index.html`
- GSAP 3.12.5 + ScrollTrigger (CDN)
- Google Fonts: Caveat + Nunito
- No build step, no framework, no npm — open index.html directly

## Repo
https://github.com/dorianguzman/AndresyKaty-website.git

## Key Conventions
- **No frameworks** — vanilla JS only, no React/Vue/etc.
- **Single file** — all CSS and JS live inside `index.html`
- **SVG illustrations** — built inline, never as external files
- **Colors from CSS vars only** — never hardcode hex in HTML attributes
- **i18n** — all user-facing text uses `data-i18n` keys; translation object at top of JS section
- **RSVP** — sends via WhatsApp to +353 83 072 4617 (`wa.me/353830724617`)

## Folder Structure
```
index.html          ← entire site
assets/             ← images used by the site
  hero.jpg          ← illustrated hero (Katia y Andrés flat illustration)
  image3.jpeg       ← venue exterior photo (replace with final venue photo)
reference/          ← inspiration material, do not serve
  *.jpeg / *.png    ← reference screenshots from brief
  pic.jpeg          ← original couple photo (replaced by hero.jpg)
  Página de bodorrio.docx
tasks/              ← session docs (this folder)
```

## Style — See tasks/handover.md for complete style guide
