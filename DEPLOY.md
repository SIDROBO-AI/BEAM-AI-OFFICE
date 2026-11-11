# Beam Office Pack — deploy instructions

Static site, no build step. Host it on GitHub Pages; Beam downloads/installs it from that URL.

## Deploy to GitHub Pages

1. Create a new public GitHub repository (e.g. `beam-office-pack`).
2. Upload the **contents** of this folder to the repo root (pack.json must sit at the root,
   next to index.html — not nested inside a subfolder).
3. Repo → Settings → Pages → Source: "Deploy from a branch" → Branch: `main`, folder: `/ (root)` → Save.
4. Wait ~1 minute. Your URL will be: `https://<your-username>.github.io/beam-office-pack/`

## Verify the deployment

Open in a browser:
- `https://<user>.github.io/beam-office-pack/pack.json` → should show JSON
- `.../quire/` → word processor with the Welcome sample document
- `.../ledger/` → spreadsheet with the Quarterly Sales sample
- `.../lectern/` → presentation editor with the Harbor & Pine sample deck

Then send the base URL to Beam for integration.

## What this pack contains

- `quire/` — Beam Write (word processor: .docx/.docm/.rtf/.md, track changes, comments, tables, mail merge, PDF export)
- `ledger/` — Beam Sheets (spreadsheet: .xlsx/.xlsm/.csv, 519 functions, charts, pivot tables, conditional formatting, PDF export)
- `lectern/` — Beam Slides (presentations: .pptx/.ppsx/.potx, transitions, animations, slide show, PDF/PNG export)
- `common/`, `fonts/`, `icons/` — shared engine, fonts, artwork
- `pack.json` — the manifest Beam's installer reads (version + app list)

## Changes made vs upstream VibeOffice

- Removed: service worker (`sw.js`), updater (`updater/`), PWA install prompts, GitHub feedback
  link, canonical/OG search-engine tags, robots/sitemap
- `common/suite.js`: `VO.offersInstall = false`; update-check endpoints neutralized
  (Beam's host handles updates, the pages never phone home)
- Added: `pack.json` (Beam pack manifest)
- License: Apache 2.0 (upstream VibeOffice) — `oss-licenses.html` retained for attribution
