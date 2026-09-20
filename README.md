# Lancaster Furnished Housing — website

Static site for **Lancaster Furnished Housing — A Home Away From Home**: fully furnished
apartments for 30+ day stays in Lancaster's West End. Rebuild of the Squarespace site
(keyboard-glockenspiel-647p.squarespace.com), built 2026-09-20 from a full scrapling capture of
that site (copy, photos, and measured brand tokens).

## Structure

- 9 pages: `index.html`, `properties.html`, `the-west-end.html`, `about-us.html`,
  `contact-us.html`, and 4 unit pages (`606-w-lemon-unit-1/2`, `407-college-ave-unit-2`,
  `409-college-ave-unit-2`).
- `assets/css/tokens.css` — design tokens (navy `#112D4E`, cream `#F5F1EA`, espresso `#362517`,
  Poppins; dark mode + reduced-motion support).
- `assets/css/styles.css` — components.
- `assets/img/` — logos + per-page photos (from the Squarespace capture).
- Matterport 3D walkthrough iframes on 606-U2 (`xUSaWrR4k2T`), 407-U2 (`Tgn7CdixdW6`),
  409-U2 (`gbpZPenFeCd`).
- Inquiry form stubbed for Formspree — **replace `YOUR_FORM_ID` in the form `action`** after
  creating the free form.

## Deploy (GitHub Pages)

1. Push to GitHub (repo owned by the GitHub account linked to `charliebk417@yahoo.com`).
2. Repo → Settings → Pages → Source: deploy from branch → `main`.
3. After it's live, update `BASE` in `sitemap.xml` to the real URL.

## TODOs

- [ ] Formspree form ID (all 5 forms: `action="https://formspree.io/f/YOUR_FORM_ID"`)
- [ ] Real Instagram link in the footer (currently an HTML comment)
- [ ] sitemap.xml `BASE` URL after deploy
