# NOC / Systems Engineer — Study Platform

A static study platform for a personal NOC / Systems Engineer learning roadmap. The original roadmap, data, and interactive features remain in place, now arranged as three linked pages: Dashboard, Roadmap, and Career & Portfolio.

## Files

- `index.html` — Dashboard and GitHub Pages entry point.
- `roadmap.html` — the complete 16-week route, with the phase overview and study tips available below it.
- `career.html` — portfolio guidance, certifications, skill gaps, study rhythm, capstone, readiness checklist, and next steps.
- `noc-roadmap.html` — matching Dashboard copy retained for compatibility.
- `noc-roadmap-original.html` — untouched copy of the original Claude export, kept as a restore point.
- `README.md` — project notes and run instructions.

The pages are self-contained HTML files with inline styling, roadmap data, the architecture diagram, and JavaScript. No build step, package manager, or local dependencies are required.

## Run locally

From this folder, run `python3 -m http.server 8000` and open `http://localhost:8000/`. The navigation uses sibling HTML pages, so serve the folder over HTTP instead of opening an individual file directly.

## Included features

The platform retains the 16-week roadmap, expandable weekly plans, study checklists and custom tasks, progress summaries, study timer, skill-gap ratings, readiness checklist, certification cards, and per-week notes. The Dashboard has one week chooser: select any week, then open it on the Roadmap page. The “Start with Week” shortcut continues to open the next incomplete week.

The same selected week is used for the study timer. A session is assigned to that week when it starts, and the chooser stays locked until the session is logged. When the chooser still points to the recommended week, it advances as progress moves forward.

The Roadmap page opens directly on the week list. Its five-phase overview and study tips remain available in a collapsed section below the route.

The Career & Portfolio page adds practical finish criteria for project READMEs, runbooks, incident evidence, safe demos, cost notes, and cleanup. Optional polish ideas do not add required weeks.

## Study route

The five phases group the existing weeks: foundations (1–5), container operations (6–7), cloud and APIs (8–10), operations and reliability (11–12), and orchestration and infrastructure as code (13–16). Phase completion is calculated from the existing weekly checklist state.

## Saved data and runtime behavior

Progress and notes are stored in browser `localStorage`, shared by the three pages on the same site and browser. Data is not committed to the public repository. Each origin has separate storage, so data from a local file or localhost does not automatically transfer to the hosted domain.

The artifact checks for Claude's `window.claude` APIs. File uploads and Claude account/database sync are available only when those APIs are present. Outside Claude, the upload control is hidden and notes and progress use browser-local storage. Google Fonts are optional and system-font fallbacks keep the page readable offline.

## Static hosting

`index.html` is at the project root and can be published as a static site. There is no build command. The GitHub Pages workflow publishes the repository root, including the linked `roadmap.html` and `career.html` pages.