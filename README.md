# My 90 Days — PWA prototype

A functional, offline-first Somali life challenge tracker covering **12 Nov 2026–9 Feb 2027**.

## Included
- Responsive dashboard, day counting and progress reports
- Daily habit tracker and fasting days (Monday/Thursday)
- Thesis submission dates from Amoud University announcement; semester classes
- Re-exam revision list; January exams/defense dates explicitly unconfirmed
- Financial transaction and debt priority tracker; opening debt $8,379
- Health, weight, walk, water and sleep logs
- JSON export/import, all data stored locally (no cloud account)
- Manifest/service worker for installation/offline access after first successful HTTPS visit

## Run locally
From this folder: `python -m http.server 8000`. In a browser visit `http://localhost:8000`.

## Install on phones
Host this folder on an **HTTPS** static web host (e.g. GitHub Pages, Netlify, Cloudflare Pages). Then open the HTTPS URL.
- Android/Chrome: menu → Install app / Add to Home Screen.
- iPhone/Safari: Share → Add to Home Screen.
- Desktop Chrome/Edge: Install icon when available.

**Opening `index.html` via `file://` may display UI but does not enable service worker/offline PWA installation.**

## Privacy and limitations
Information is saved only in that browser's `localStorage`; it **does not synchronize across devices**. Export JSON backup regularly and keep it private because it may contain sensitive habit and debt entries. Clearing site data loses your entries. Offline availability depends on a successful initial HTTPS load. No push reminders, user accounts or server are included in the prototype.

This is an MVP, not a medical diagnostic app. Testosterone is *suspected*, not confirmed. Financial payment dates and January exams are not invented.

## v2 — Jadwal & Cibaado
- **Jadwal** tab: 24-hour timeline, editable dated entries, completion checkboxes, official class blocks.
- Five separate prayers: manually entered local prayer times, actual prayed time, completion and jamaaco/home/other location.
- Morning/evening adhkar, tasbih and duas tracked individually with counts.
- Quran and reading sessions with start and end times and total durations.
- Existing localStorage key `my90days-v1` retained to preserve v1 records after deploying v2. Back up first.
- Prayer calculations are NOT automatic. Enter verified local times each date.
- Deploy updated files (including sw.js) to GitHub Pages and reload.

## v3 — N90 discreet private tracker
- `N90` is a neutral section title; no explicit sensitive habit name appears in dashboard or navigation.
- 90 day tick grid and Somali motivational messages. PIN-gated view is a *casual privacy screen*, **not** encrypted storage; localStorage and exported backup are plain text.
- Existing v1 habit data is left intact; the old sensitive habit row is hidden from general UI.
- Date-specific five-prayer location and actual prayer time; adhkar/tasbih/duas individual checks; 24 hour timeline and session timers.
- On deployment replace **all files**, not only `index.html`, to update service worker cache. Back up first.
