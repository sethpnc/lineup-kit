# Storm Baseball

Coach toolkit for the Storm 13–15 rec team: roster, lineup rules, and a small **static website** for lineups, diamonds, and scouting.

Open [`index.html`](index.html) in a browser (home page).

## Live site

**URL:** https://sethpnc.github.io/lineup-kit/

GitHub Pages publishes the repo root from the **`main`** branch. There is no separate web server.

To update the live site: commit your changes, then `git push origin main` (or merge a pull request into `main`). Commits on other branches do not go live. Give Pages a minute, then hard-refresh if you still see the old page.

The whole repo is public at that URL, including files under `data/` that the hub does not link.

## Folders

| Path | What lives here |
|------|-----------------|
| [`index.html`](index.html) | Hub: scouting + each game’s web lineup and diamond |
| [`games/`](games/) | **Web** game pages (`game-XX/lineup.html`, `diamonds.html`) |
| [`scouting.html`](scouting.html) | **Web** team scouting report |
| [`print/`](print/) | Letter-size HTML (and PDFs when generated) for paper |
| [`data/`](data/) | Source of truth: roster, stats CSV, lineup YAML, coach summaries, logo master |
| [`assets/`](assets/) | Logo + shared CSS for the site |

YAML for a game stays in [`data/games/`](data/games/). HTML for that game’s **screen** view lives under [`games/game-XX/`](games/). **Print** HTML stays only under [`print/`](print/).

## Quick edit

- Roster: [`data/roster.yaml`](data/roster.yaml)
- Stats: [`data/stats/stats.csv`](data/stats/stats.csv) (replace exports; do not merge)
- Rules: [`data/lineup-rules.yaml`](data/lineup-rules.yaml)

## Print

Design notes: [`print/README.md`](print/README.md). Open a print HTML and `Cmd+P`, or use a PDF under `print/pdf/` if present.

## Coach pre-game summary

Private markdown (not on the site): ask for a **coach summary**. Spec: [`data/games/COACH-SUMMARY.md`](data/games/COACH-SUMMARY.md).
