# Sleeper GM

Responsive, read-only fantasy football dashboard for **plasmiz**, league **1413584821648687104**. Built with plain HTML, CSS, and JavaScript; no build step, secret, or paid service required.

## Features
- Live league metadata, roster and injury/bye flags
- Standings by win percentage and points for; points for and against
- Week 1–18 matchups with actual scores and commissioner overrides
- Transactions, including player moves and traded picks
- Roster search and starter/bench/reserve filters
- Manual refresh and five-minute refresh while visible
- Player database cached locally for 24 hours per Sleeper guidance

## Run locally
`python3 -m http.server 8080`

Open http://localhost:8080. Requests go directly to https://api.sleeper.app/v1. The API is read-only. Player status and scores may be delayed. No projections or predictive recommendations are represented as live data.

## Deploy
GitHub Pages serves `main` from `/` at https://plasmizx2.github.io/sleeper-gm/ . Configure Settings → Pages → Deploy from a branch → main → /(root). `.nojekyll` keeps this a static site.

API documentation: https://docs.sleeper.com/

## Verified roster endpoint
`https://plasmizx2.github.io/sleeper-gm/roster.json` is plain JSON, readable without JavaScript. It identifies plasmiz by Sleeper user ID, includes all current player names/IDs and starter, bench, reserve and taxi assignments, and records `verified_at` and `expires_at` in UTC.

GitHub Actions refreshes and deploys it every three hours (00:17, 03:17, etc. UTC), on pushes, or manually. Scheduled runs may be delayed by GitHub; they are not exact-time guarantees. Failed verification preserves the last snapshot and fails the run. Consumers must reject expired snapshots (four-hour freshness window), fetch directly from Sleeper if possible, or withhold player-specific advice. This workflow refreshes roster data; it does not generate or modify a ChatGPT scheduled GM report.
