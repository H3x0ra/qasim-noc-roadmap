# NOC / Systems Engineer — Study Platform

A static study platform for a personal NOC / Systems Engineer learning roadmap. The original roadmap and interactive features are kept across three linked pages: Dashboard, Roadmap, and Career & Portfolio.

## Files

- `index.html` — Dashboard and GitHub Pages entry point.
- `roadmap.html` — the complete 16-week route, with the phase overview and study tips below it.
- `career.html` — portfolio guidance, certifications, skill gaps, study rhythm, capstone, readiness checklist, and data backup controls.
- `noc-roadmap.html` — matching Dashboard copy retained for compatibility.
- `noc-roadmap-original.html` — untouched copy of the original Claude export.

The pages are self-contained HTML files with inline styling, roadmap data, the architecture diagram, and JavaScript. No build step, package manager, or local dependencies are required.

## Run locally

From this folder, run `python3 -m http.server 8000` and open `http://localhost:8000/`. The navigation uses sibling HTML pages, so serve the folder over HTTP instead of opening an individual file directly.

## Features

The platform retains the 16-week roadmap, expandable weekly plans, study checklists and custom tasks, progress summaries, study timer, skill-gap ratings, readiness checklist, certification cards, and per-week notes. On the Dashboard, choose any week and open it directly. The “Start with Week” shortcut still opens the next incomplete week.

The timer saves its duration, selected week, and running or paused state in this browser. It resumes when you move between the Dashboard, Roadmap, and Career pages. Logged time goes to the week assigned when the session starts.

The Roadmap opens on the weekly list. Its five-phase overview and study tips remain available below the route. The Career & Portfolio page keeps the original certification and role-readiness guidance and adds practical finish criteria for project READMEs, runbooks, incident evidence, safe demos, cost notes, and cleanup.

## Saved data and backups

Progress and notes use this browser's local storage and are shared by the three pages on the hosted site. Notes save immediately as you type. GitHub Pages serves static files and does not provide a user account or database, so data does not automatically sync to another browser or device.

On the Career & Portfolio page, **Download backup** saves checklists, progress, and notes to a JSON file. **Restore backup** imports that file into this browser and replaces its current saved progress and notes after confirmation. Keep the backup file somewhere safe if you want a copy outside this browser. It is not sent to a server.

The original Claude artifact checks for `window.claude` APIs. File uploads and Claude account/database sync are available only when those APIs are present. On the hosted static site, notes and progress are stored locally. Google Fonts are optional and system-font fallbacks keep the page readable offline.

## Static hosting

`index.html` is at the repository root. The GitHub Pages workflow publishes the root directly, including `roadmap.html` and `career.html`.