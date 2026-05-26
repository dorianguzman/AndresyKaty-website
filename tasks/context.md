# Context — Corrections & Project Rules

Format: `[YYYY-MM-DD] | what went wrong | rule to prevent it`

---

[2026-05-26] | Hero was initially set to pic.jpeg (couple photo) but user provided a flat illustrated version | hero.jpg = the illustration. pic.jpeg = original photo (in reference/). Never swap them back.

[2026-05-26] | Reference images and docx were left in repo root alongside site files | Reference material always goes in reference/. Active site assets always go in assets/. Keep root clean.

[2026-05-26] | RSVP was built showing a thank-you message only, with no actual delivery mechanism | RSVP must always send to WhatsApp +353 83 072 4617 (wa.me/353830724617). Form opens WhatsApp in new tab with pre-filled Spanish message, then shows thanks screen.

[2026-05-26] | image3.jpeg (venue photo) is used by the site — must not be moved to reference/ | Only move assets to reference/ when they are no longer referenced in index.html. Always grep before moving.
