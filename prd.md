# PRD — Lancaster Furnished Housing website v2 (static rebuild)

Status: draft v1 for review (2026-09-20) · Owner: Charles & Shannon · Replaces the Squarespace
build. This is the last free checkpoint before code — review and edit before implementation
(icm-website-builder step 5).

## 1. Product

A static site hosted on GitHub Pages for "Lancaster Furnished Housing — A Home Away From Home":
the portfolio's own public presence, driving direct booking inquiries to
`LancasterFurnishedHousing@gmail.com`. Audience: mid-term (30+ day) furnished-stay guests —
professionals, families in transition, relocation partners.

## 2. Pages (v1)

| Page | File | Content source |
| --- | --- | --- |
| Home | `index.html` | hero + 3 value props ("Well equipped. / Managed with Care. / Feels like home."), CTA → properties |
| Properties | `properties.html` | 6 unit cards, linked to detail pages |
| The West End | `the-west-end.html` | neighborhood guide (capture copy) |
| About Us | `about-us.html` | capture copy |
| Contact Us | `contact-us.html` | phone/email + inquiry form |
| Unit: 606-U1 | `606-w-lemon-unit-1.html` | capture copy, photos, NO 3D scan |
| Unit: 606-U2 | `606-w-lemon-unit-2.html` | capture copy, photos, Matterport `xUSaWrR4k2T` |
| Unit: 407-U2 | `407-college-ave-unit-2.html` | capture copy, photos, Matterport `Tgn7CdixdW6` |
| Unit: 409-U2 | `409-college-ave-unit-2.html` | capture copy, photos, Matterport `gbpZPenFeCd` |

3D embeds use the official Matterport iframe from each property's `*_3DSCAN_INDEX_2026-09.md`
(online embed = ToS-safe; archives are offline backup).

## 3. Design tokens (measured from the live site)

- Type: Poppins (300/400/500/700) via Google Fonts; fallback stack system sans.
- Colors:
  - `--accent: #112D4E` (navy — buttons, headings, links)
  - `--cream: #F5F1EA` (section backgrounds)
  - `--espresso: #362517` (footer, dark sections, alt CTA)
  - `--ink: #1A1A1A` / `--paper: #FFFFFF`
- Type scale (clamp(), mom-site pattern): hero 2.25–3.75rem, h2 1.5–2rem, lead 1.25rem,
  body 1rem, small .875rem.
- Header: logo-color.png left, nav right (Home/Properties/The West End/About Us/Contact Us).
- Footer: espresso background, logo-nobg.png, phone/email, copyright.
- Components: unit card (photo, name, beds/baths, "View unit" link), gallery grid, inquiry form
  (navy button, cream inputs), Matterport iframe section (16:9, lazy).

## 4. Inquiry form (Formspree)

Fields (from `marketing/spec.md`): Name*, Email*, Phone, Property/unit* (prefilled per page),
Move-in date*, Length of stay* (1–3/3–6/6+ mo/not sure), Guests incl. pets, Message, consent
checkbox + privacy line. Action `https://formspree.io/f/<FORM_ID>` — **FORM_ID TBD** (user
creates the free Formspree form; stub + comment until then). Guardrails: no financial fields,
30-day-minimum stated in copy, consent required.

## 5. Non-goals (v1)

- No booking/payment engine (inquiries only; payment stays TurboTenant/Zelle/Venmo).
- No 605/602/6232-Monterey/522/325/917 pages (later per business decisions).
- No tenant names, claim material, or internal/back-office content (privacy + Fair Housing —
  run `fair-housing-compliance-overlay` before publishing).

## 6. Quality bar (design QA standing in for web-design-guidelines/design-taste-frontend)

- No AI-default typography (no Inter; Poppins is the brand font — from the reference).
- Dark mode via `prefers-color-scheme` (cream → dark equivalents).
- `prefers-reduced-motion` guard on all transitions/hover effects.
- Alt text on every image; labels on form fields; semantic HTML; no em-dashes in copy.
- Lighthouse-sane: lazy images, single Google Fonts request, no JS frameworks.

## 7. Delivery checklist

- [ ] tokens.css + styles.css written from §3 values
- [ ] 9 HTML pages built per §2 with capture copy
- [ ] 4 unit pages: photos from zip + Matterport iframes per §2
- [ ] Properties cards link to detail pages (live-site bug fixed)
- [ ] Inquiry form stubbed (Formspree FORM_ID comment) on unit + contact pages
- [ ] Header/footer with the two logo files; real Instagram TODO
- [ ] GitHub repo (yahoo-linked account) + Pages enabled + pathing verified live
- [ ] CHANGELOG + backup after deploy

## 8. Open questions (owner)

1. Formspree form ID (create at formspree.io, paste the `f/<id>` here).
2. Instagram handle for the footer.
3. GitHub repo name: `lancaster-furnished-housing` (confirm).
4. Custom domain later? (GitHub Pages subdomain for now.)
