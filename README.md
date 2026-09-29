# NOC / Systems Engineer — Study Platform

A static, single-page study dashboard for a personal NOC / Systems Engineer learning roadmap. The original Claude Artifact source is preserved in `noc-roadmap.html`. `index.html` is an identical copy that makes the site load from the root when served by a static host such as GitHub Pages.

## Files

- `index.html` — static-host entry point; identical to the original HTML source.
- `noc-roadmap.html` — the original exported Claude Artifact, unchanged.
- `README.md` — project notes and run instructions.

The HTML contains the page structure, styling, roadmap data, inline SVG architecture diagram, and JavaScript. No build step, package manager, or local dependencies are required.

## Run locally

Open `index.html` in a browser. To serve it over HTTP instead, run `python3 -m http.server 8000` from this folder and visit `http://localhost:8000/`.

## Included features

The dashboard has the 16-week roadmap, expandable weekly plans, study checklists and custom tasks, progress summaries, study timer, skill-gap ratings, readiness checklist, certification cards, and per-week notes. Progress and notes are stored in browser `localStorage`; each origin has separate storage, so data from a `file://` page, localhost, and a hosted domain will not automatically transfer between them.

## Runtime-specific behavior

The artifact checks for Claude's `window.claude` APIs. File uploads and Claude account/database sync are available only when those APIs are present. Outside Claude, the upload control is hidden; notes and progress use browser-local storage. The Google Fonts are optional and have system-font fallbacks, so the page remains readable offline.

## Static hosting

`index.html` is at the project root and can be published as a static site. There is no build command. If publishing from a GitHub branch, configure Pages to serve the repository root (or place these files in the selected publishing folder).
