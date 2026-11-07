# Sleeper GM

Responsive, read-only fantasy football dashboard for **plasmiz**, league **1413584821648687104**. Built with plain HTML, CSS, and JavaScript; no build step, secret, or paid service required.

## Features
- Live league metadata, roster and injury/bye flags
- Standings by win percentage and points for; FAAB balances
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
