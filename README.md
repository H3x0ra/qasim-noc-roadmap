# NOC / Systems Engineer — Study Platform

A static, single-page study dashboard for a personal NOC / Systems Engineer learning roadmap. The original roadmap, data, and interactive features remain in place. `index.html` is the GitHub Pages entry point; `noc-roadmap.html` remains a matching standalone copy.

## Files

- `index.html` — static-host entry point for GitHub Pages.
- `noc-roadmap.html` — standalone copy of the dashboard.
- `noc-roadmap-original.html` — untouched copy of the original Claude export, kept as a restore point.
- `README.md` — project notes and run instructions.

The HTML contains the page structure, styling, roadmap data, inline SVG architecture diagram, and JavaScript. No build step, package manager, or local dependencies are required.

## Run locally

Open `index.html` in a browser. To serve it over HTTP instead, run `python3 -m http.server 8000` from this folder and visit `http://localhost:8000/`.

## Included features

The dashboard has the 16-week roadmap, five live phase cards, expandable weekly plans, study checklists and custom tasks, progress summaries, study timer, skill-gap ratings, readiness checklist, certification cards, and per-week notes. New guidance helps turn weekly work into portfolio evidence and gives optional polish ideas that do not add required weeks. Progress and notes are stored in browser `localStorage`; each origin has separate storage, so data from a `file://` page, localhost, and a hosted domain will not automatically transfer between them.

## Study and portfolio guidance

The five phases group the existing weeks: foundations (1–5), container operations (6–7), cloud and APIs (8–10), operations and reliability (11–12), and orchestration and infrastructure as code (13–16). Phase completion is calculated from the existing weekly checklist state.

The portfolio section adds practical finish criteria for project READMEs, runbooks, incident evidence, safe demos, cost notes, and cleanup. Optional ideas are explicitly separated from the 16-week core route.

## Runtime-specific behavior

The artifact checks for Claude's `window.claude` APIs. File uploads and Claude account/database sync are available only when those APIs are present. Outside Claude, the upload control is hidden; notes and progress use browser-local storage. The Google Fonts are optional and have system-font fallbacks, so the page remains readable offline.

## Static hosting

`index.html` is at the project root and can be published as a static site. There is no build command. If publishing from a GitHub branch, configure Pages to serve the repository root (or place these files in the selected publishing folder).
