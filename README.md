# Storm Baseball

Coach toolkit for the Storm 13–15 rec baseball team: editable roster, lineup rules, and (next) pre-game 5-inning lineup generation.

## Quick edit

Open [`data/roster.yaml`](data/roster.yaml):

- Change a player’s **position priority** by reordering the `positions` list
- Add notes under `strengths`, `weaknesses`, or `notes`

Numeric stats live in [`data/stats/stats.csv`](data/stats/stats.csv). Rules defaults live in [`data/lineup-rules.yaml`](data/lineup-rules.yaml).

## Print a game sheet

When a lineup is locked, open the matching file under [`print/`](print/) (e.g. [`print/game-01.html`](print/game-01.html)) and print to PDF/paper. Design notes: [`print/README.md`](print/README.md).

## Coach pre-game summary

For your eyes only (lineup + positions + sits), ask for a **coach summary**. Spec: [`data/games/COACH-SUMMARY.md`](data/games/COACH-SUMMARY.md). Example: [`data/games/game-01-coach-summary.md`](data/games/game-01-coach-summary.md).

## Status

- [x] Roster imported (13 players)
- [x] Sample Game 1 rotation + printable sheet
- [x] Coach pre-game summary report (repeatable)
- [ ] Lineup generator / pre-game workflow
- [ ] Game plan history
