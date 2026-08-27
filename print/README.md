# Printable lineup design

Single **letter-size** sheet used every time a game plan is finalized.

## Layout (always the same)

1. **Masthead** — Storm logo + `GAME LINEUP` + game #
2. **Game meta** — Opponent / Date / Field·Time (hand-fill)
3. **Left: Batting order** — single vertical strip, full names 1–13
4. **Right: Defense matrix** — large cells for pen edits; positions × innings 1–5; bench row
5. **Footer** — pitch plan + standing rules

## Visual system

| Token | Role |
|--------|------|
| Storm red (`#c8102e`) | Text accents, red rules/borders (no solid fills) |
| Black (`#0a0a0a`) | Ink, table borders (no solid header fills) |
| Very light red tint | Pitching row only |
| Light gray | Bench row only |
| Logo | `data/storm-logo.png` |

Avoid solid red or black background blocks — they print heavy and muddy.

## Diamond views (optional)

- **Web (interactive):** [`game-01-diamond-web.html`](game-01-diamond-web.html) — one diamond, switch innings
- **Print (6-up):** [`game-01-diamonds-print.html`](game-01-diamonds-print.html) — letter page, innings 1–5 filled + blank inning 6 for write-ins

## Team scouting report

One-page printable batting snapshot (logo + team totals + player table + strengths): [`team-scouting-report.html`](team-scouting-report.html). Rebuild after updating `data/stats/stats.csv`.

## How to print

1. Open the game HTML (e.g. [`game-01.html`](game-01.html) or [`game-01-diamonds-print.html`](game-01-diamonds-print.html))  
2. `Cmd+P` → PDF or printer  
3. Enable **background graphics** if you want grass/dirt tints  

## Agent workflow

When the coach finalizes a lineup:

1. Save/update `data/games/game-XX-lineup.yaml`
2. Write/update `print/game-XX.html` from this template + `lineup.css`
3. Leave opponent/date/field blank unless provided
4. Defense cells stay large (write-in friendly); batting stays compact on top
5. Optionally refresh diamond web + print pages if those are in use
