# BRIEFING — Lancaster Furnished Housing v2 build

Analysis handoff for the build (icm-website-builder steps 1–2: reference analyzed, facts
written down for the builder). Everything below is measured or copied, not invented.

## Reference material

- Squarespace capture (2026-09-20): `marketing/site-capture/` — html/ (raw pages) + md/ (copy).
- Site images: `lancaster_storage/marketing/lancaster-furnished-housing/images/LFH_SITE_IMAGES_2026-09.zip`
  — 154 images + `MANIFEST.csv` (URL → filename). Filenames are `NNN_`-prefixed (Squarespace
  reuses names like `01.jpg` across folders).
- Logos: `assets/img/logo-color.png` (header) + `assets/img/logo-nobg.png` (footer/light bg) —
  the exact files the live site uses. Full logo set: `marketing/assets/logos/`.
- Booking form: `marketing/spec.md` (fields, guardrails).
- 3D scans: per-property `*_3DSCAN_INDEX_2026-09.md` files (Matterport iframe snippets).

## Brand (measured from the live site's generated stylesheet)

- Font: **Poppins** (weights 300/400/500/700) — Google Fonts.
- Colors (Squarespace tokens, converted to hex):
  - Accent: `hsl(212.46, 64.21%, 18.63%)` → **#112D4E** (deep navy) — primary buttons, headings.
  - Light accent: `hsl(35, 40%, 94.12%)` → **#F5F1EA** (warm cream) — section backgrounds.
  - Dark accent: `hsl(32.9, 40.26%, 15.1%)` → **#362517** (espresso) — footer/dark sections.
  - Neutrals: white `#FFFFFF`, black `#000000`.
- Voice: warm, "Managed with Care. / Well equipped. / Feels like home." — mid-term furnished
  stays, not nightly rentals.

## Site map v1 (agreed scope)

1. `index.html` — Home (hero, 3 value props, CTA → properties).
2. `properties.html` — 6 unit cards (606-U1, 606-U2, 407-U2, 409-U2, 608-U1 "Coming Soon!",
   608-U2 "Coming Soon!"). Cards MUST link to their detail pages (fixes the live-site bug).
3. `the-west-end.html` — neighborhood guide (cafes/restaurants/markets/parks/arts/universities —
   copy in `site-capture/md/the-west-end.md`).
4. `about-us.html` — copy in `site-capture/md/about-us.md`.
5. `contact-us.html` — phone (310) 749-0680, LancasterFurnishedHousing@gmail.com + inquiry form.
6. Four unit detail pages (copy from `site-capture/md/608-west-lemon-street-unit-2*.md`):
   - `606-w-lemon-unit-1.html` (1BR/1BA; no 3D scan — photos only)
   - `606-w-lemon-unit-2.html` (2BR/1BA) — Matterport `xUSaWrR4k2T`
   - `407-college-ave-unit-2.html` (2BR/1BA) — Matterport `Tgn7CdixdW6`
   - `409-college-ave-unit-2.html` (2BR/1BA) — Matterport `gbpZPenFeCd`
7. No 605/602/6232-Monterey pages in v1 (user decision). 608 detail pages later (scan
   `tocUKygscSw` ready when 608-U1 launches).

## Form (Formspree)

Fields per `marketing/spec.md`: name, email, phone, property/unit (prefilled), move-in date,
length of stay, guests incl. pets, message, consent checkbox + privacy line. Action URL:
`https://formspree.io/f/<FORM_ID>` — FORM_ID TBD, stub with a placeholder + comment.

## Known fixes vs. current site

- Link Properties cards → detail pages (live site doesn't).
- Instagram footer: real handle TBD — leave an obvious TODO, no squarespace.com placeholder.
- Titles/SEO per page (live site's are Squarespace defaults like "Gallery 1").

## Architecture (mom-site pattern)

- `tokens.css` — all design tokens (colors, Poppins stack, clamp() type scale, spacing).
- `styles.css` — components (header/nav, hero, cards, gallery, form, footer).
- Static HTML only; no build toolchain (FAT32 rule). GitHub Pages, root-relative paths.
