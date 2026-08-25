# KELLY HQ

Live project hub for the Kelly Residence — agenda, schedule, plans, interiors, VE, recaps, and Decisions.

## Pages
- `index.html` — Project HQ dashboard
- `decisions.html` — Decisions app (mobile-first)

Both are self-contained single files. Data is read live from the project Google Sheet via a deployed Apps Script endpoint, so the pages stay current without a rebuild.

## Publishing
This folder is the GitHub Pages root. In the repo: **Settings → Pages → Source: Deploy from a branch → Branch: main → Folder: /docs**.

Site URL: `https://<owner>.github.io/<repo>/`

## Rebuilding
These files are compiled bundles. Edit the sources (`Project HQ.dc.html`, `Decisions.dc.html`) in the design project, re-bundle, and replace the two files here.
