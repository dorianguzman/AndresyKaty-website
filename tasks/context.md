# Context — Corrections & Project Rules

Format: `[YYYY-MM-DD] | what went wrong | rule to prevent it`

---

[2026-05-26] | Hero was initially set to pic.jpeg (couple photo) but user provided a flat illustrated version | hero.jpg = the illustration. pic.jpeg = original photo (in reference/). Never swap them back.

[2026-05-26] | Reference images and docx were left in repo root alongside site files | Reference material always goes in reference/. Active site assets always go in assets/. Keep root clean.

[2026-05-26] | RSVP was built showing a thank-you message only, with no actual delivery mechanism | RSVP must always send to WhatsApp +353 83 072 4617 (wa.me/353830724617). Form opens WhatsApp in new tab with pre-filled Spanish message, then shows thanks screen.

[2026-05-26] | image3.jpeg (venue photo) is used by the site — must not be moved to reference/ | Only move assets to reference/ when they are no longer referenced in index.html. Always grep before moving.

[2026-05-26] | User said "make the band transparent" — I restructured the whole layout AND changed all text colors | Only change exactly what was asked. "Transparent background" = change background property only. Never touch text colors, layout, or structure unless explicitly told to.

[2026-05-26] | Location band transparency: user ultimately reverted to solid garnet — do not attempt to make it transparent again unless user explicitly asks | The solid garnet band on the location section is intentional. Leave it.

[2026-05-26] | GSAP parallax on location image was pushing image DOWN (yPercent 0→25), revealing body background at top | Always use fromTo with negative start value for parallax: fromTo(-15, 10). Image must always cover its container top.

[2026-05-26] | TheSkinny font has tight spacing around openers and accented letters | Rules for --font-skinny text: (1) always apply letter-spacing: 0.06em; (2) add a space after ¿ and ¡ openers; (3) add a space after every accented letter (á, é, í, ó, ú, ñ) when immediately followed by another letter.
