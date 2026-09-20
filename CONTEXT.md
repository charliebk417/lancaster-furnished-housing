# lancaster-furnished-housing/ — Website v2 Project

The rebuild project for the portfolio's own site, brand "Lancaster Furnished Housing — A Home
Away From Home" (currently live in Squarespace as `keyboard-glockenspiel-647p.squarespace.com`,
private/unpublished).

## Layout (follows the circus `factories/website/` pattern)

Circus keeps each site as its own project folder (its own git repo: `CONTEXT.md`, `prd.md`,
`index.html`, `assets/`, version folders) inside a `factories/website/` container. Here `marketing/`
is the container and this folder is the project.

- Planning docs live in `marketing/prd.md` + `marketing/spec.md` (the factory container's briefs) —
  copy them into this folder when the build starts as its own repo (circus keeps `prd.md`
  inside each project).
- `marketing/site-capture/` — the 2026-09-20 scrapling capture of the current Squarespace site
  (page copy + raw HTML) — the reference material this project rebuilds from.
- `marketing/assets/` — brand logos + review/listing screenshots.

## Content mirror (Dropbox `lancaster_storage/`)

Large site content mirrors this folder's path in the Dropbox mirror (per
`docs/specs/MEDIA-STORAGE.md`):

- **Site images**: `lancaster_storage/marketing/lancaster-furnished-housing/images/LFH_SITE_IMAGES_2026-09.zip`
  — one zip (Dropbox-friendly, same convention as the 3D scans) containing the 153 unique
  images referenced by the captured site pages + a `MANIFEST.csv` (URL → filename). Filenames
  are prefixed `NNN_` because Squarespace reuses names like `01.jpg` across folders.
- Small files (HTML/MD/source) stay on this USB — the mirror holds only large media.

## Tooling rules (this USB is FAT32)

- Source files (HTML/CSS/JS/MD) are fine here.
- NO `node_modules`, venvs, or symlink-dependent toolchains on this drive — build/deploy
  tooling runs from the Mac's disk only (see `greenhouse/CONTEXT.md` scrapling entry for the
  same rule). Deploy reference: circus `factories/website/vercel-deployment-guide.md`
  (GitHub → Vercel, custom domain) + workspace-local skill `icm-website-builder`.

## Git/GitHub note

- Workspace repo commits are signed `Charles Hofheimer <charliebk417@yahoo.com>` (repo-local).
- GitHub CLI on this Mac is currently authed as `circuscoder` — decide account handling before
  pushing this site's repo (see CHANGELOG/open items).

## Build state (2026-09-20)

v2 static site built in this folder: 9 pages (Home, Properties, West End, About, Contact, 4 unit
pages), `tokens.css` + `styles.css` (Squarespace-measured navy/cream/espresso + Poppins), Matterport
3D embeds on 606-U2/407-U2/409-U2, Formspree form stubs, photos copied from the capture zip.
Own git repo (initial commit done, author `charliebk417@yahoo.com`).

Live (2026-09-20): https://charliebk417.github.io/lancaster-furnished-housing/ — repo
github.com/charliebk417/lancaster-furnished-housing (public, owner = yahoo-linked account),
GitHub Pages from `main` (HTTPS enforced). Local pushes go through `gh` (run `gh auth setup-git`
once per machine).

Still open: real Formspree form ID, real Instagram handle, owner review of the PRD checklist.
