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

## Open items (from site-capture findings)

1. Properties page cards don't link to the 4 unit detail pages — fix in rebuild.
2. Instagram footer icon is the Squarespace placeholder.
3. 608-U1 / 608-U2 pages were "Coming Soon!" — decide content.
