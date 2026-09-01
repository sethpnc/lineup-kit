# Printable sheets

Letter-size HTML used for paper/PDF. **Web** lineups and diamonds live under [`../games/`](../games/), not here.

## Files

| Sheet | File |
|--------|------|
| Game 1 lineup | [`game-01-lineup.html`](game-01-lineup.html) |
| Game 1 diamonds (6-up) | [`game-01-diamonds.html`](game-01-diamonds.html) |
| Game 2 lineup | [`game-02-lineup.html`](game-02-lineup.html) |
| Game 2 diamonds (6-up) | [`game-02-diamonds.html`](game-02-diamonds.html) |
| Game 2 scoring | [`game-02-scoring.html`](game-02-scoring.html) |
| Team scouting (1 page) | [`team-scouting-report.html`](team-scouting-report.html) |

Shared styles: [`lineup.css`](lineup.css), [`scoring-sheet.css`](scoring-sheet.css). Logo: [`../assets/storm-logo.png`](../assets/storm-logo.png) (copy of `data/storm-logo.png`).

PDFs (when generated) go in [`pdf/`](pdf/).

## Layout (lineup)

1. **Masthead** — Storm logo + `GAME LINEUP` + game #
2. **Game meta** — Opponent / Date / Field·Time
3. **Left: Batting order** — first name + last initial
4. **Right: Defense matrix** — positions × innings 1–5; bench row
5. **Footer** — pitch plan + standing rules

## Visual system

| Token | Role |
|--------|------|
| Storm red (`#c8102e`) | Text accents, red rules/borders (no solid fills) |
| Black (`#0a0a0a`) | Ink, table borders (no solid header fills) |
| Very light red tint | Pitching row only |
| Light gray | Bench row only |

Avoid solid red or black background blocks.

## How to print

1. Open the print HTML  
2. `Cmd+P` → PDF or printer  
3. Enable **background graphics** if you want grass/dirt tints  

## Agent workflow

When the coach finalizes a lineup:

1. Save/update `data/games/game-XX-lineup.yaml`
2. Write/update **web** `games/game-XX/lineup.html` and `diamonds.html`
3. Write/update **print** `print/game-XX-lineup.html` (and diamonds / scoring as needed)
4. Keep opponent/date/field blank unless provided
5. Names on every print/web sheet: **first name + last initial**. Full names in YAML / roster only.
6. Update [`index.html`](../index.html) when adding a new game
