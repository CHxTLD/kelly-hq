# KELLY HQ

Live project hub for the Kelly Residence — agenda, schedule, plans, interiors, value engineering, and decisions.

## Pages
- `index.html` — Project HQ dashboard (the install target)
- `decisions.html` — Decisions app (mobile-first)

Both are self-contained single files. Data is read live from the project Google Sheet via a deployed Apps Script endpoint, so the pages stay current without a rebuild. The last successful load is cached, and a baked snapshot ships in the page — so a phone with no signal on site still shows the most recent state.

## Install to a phone
Open the site in Safari or Chrome and choose **Add to Home Screen**. It launches full-screen with no address bar. `manifest.webmanifest` and `icons/` drive the name and icon; Decisions and Value Engineering are listed as app shortcuts.

## Value engineering
The VE chapter reads the **VE Master List** spreadsheet directly and writes status flips back to it. Accept / Deciding / Reject map to the sheet's own Accepted / Proposed / Rejected wording, so the master list stays readable to anyone who opens it in Sheets.

Anyone with the link can set a status — there is no name picker on VE by design. Each card shows when it last changed, which is the signal that two people are disagreeing.

CONFIG keys that drive it:

| Key | Meaning |
| --- | --- |
| `ve_sheet` | Spreadsheet id (or full URL) of the VE master list |
| `ve_tab` | Optional tab name; first sheet if blank |
| `ve_target` | Optional savings target for the progress readout |

## Publishing
This folder is the GitHub Pages root. In the repo: **Settings → Pages → Source: Deploy from a branch → Branch: main → Folder: /docs**.

Site URL: `https://<owner>.github.io/<repo>/`

## Rebuilding
These files are compiled bundles. Edit the sources (`Project HQ.dc.html`, `Decisions.dc.html`) in the design project, re-bundle, and replace `index.html` / `decisions.html` here. The Apps Script backend lives in `apps-script/Code.gs`.
