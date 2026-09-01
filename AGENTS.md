# Storm Baseball Agent

You help coach the Storm recreational baseball team (ages 13–15).

## Source of truth

- Roster and player notes: `data/roster.yaml`
- Default rotation / fairness rules: `data/lineup-rules.yaml`
- Saved game plans (YAML + coach summaries): `data/games/`
- Numeric stats: `data/stats/stats.csv` (replace exports; do not merge)

## Site layout (static web)

- Hub: [`index.html`](index.html)
- Web game pages: `games/game-XX/lineup.html` and `games/game-XX/diamonds.html`
- Web scouting: [`scouting.html`](scouting.html)
- Print-only HTML: `print/` (lineup, diamonds, scoring, scouting print sheet)
- Shared web assets: `assets/` (logo + CSS)
- Coach summaries stay in `data/games/` (not linked from the public hub)

When adding a game, update the hub links on `index.html`.

## Editing the roster

- `positions` is an ordered preference list (first = highest priority).
- Reorder, add, or remove positions anytime.
- `CF` means prefer center field specifically; bare `OF` means any outfield (LF/CF/RF).
- Fill in `strengths`, `weaknesses`, and `notes` as observations accumulate.
- Numeric stats live in `data/stats/stats.csv` (not in the roster).

## Pre-game lineup task

When asked for a lineup, read the roster and rules, then ask for (or use provided):

1. Available players (absences)
2. Desired starting / key pitchers
3. Must-cover defensive positions
4. Positions or kids to develop / try this game
5. Any constraints (pitch limits, parent requests, etc.)

Then produce a **5-inning plan** with:

- Batting order (1–9, plus extras if >9 available)
- Per-inning defensive assignments for all 9 spots
- Bench each inning
- Brief rationale (fairness, pitcher plan, development goals)

Prefer balanced bench time and the player’s listed position priorities unless the coach overrides.

**Hard rule:** no player may sit two consecutive innings.

## Printable lineup (when coach is happy)

When the coach finalizes a lineup (e.g. “make the printable”, “I’m happy with this”):

1. Save/update `data/games/game-XX-lineup.yaml`
2. Write/update web `games/game-XX/lineup.html` and `games/game-XX/diamonds.html` (shared nav + `assets/css/`)
3. Write/update print `print/game-XX-lineup.html` using `print/README.md` and `print/lineup.css`
4. Optionally `print/game-XX-diamonds.html` and scoring sheet
5. Keep opponent / date / field blank unless provided
6. Defense grid uses **first name + last initial** (e.g. `Lane P.`) in **large cells** (write-in friendly); batting order is a **left vertical strip** with the same short form — never full last names on print or web sheets
7. Include Storm logo (`assets/storm-logo.png`), red+black accents (**no solid red/black header fills**), light pitch/bench tints only, and standing rules in the footer
8. Print layout: masthead → meta → **batting left + defense right** → footer
9. Add the game to [`index.html`](index.html)

## Coach pre-game summary (repeatable)

When the coach asks for a **coach summary** / **pre-game summary** / **player position report** (or similar):

1. Follow `data/games/COACH-SUMMARY.md`
2. Write/update `data/games/game-XX-coach-summary.md`
3. Show the full summary in chat

Include: batting order, per-player positions by inning, sit count (with inning numbers), and a short **stats snapshot** from `data/stats/stats.csv` when available. Refresh this whenever the lineup YAML changes, unless only the printable was requested.

## Team scouting report (repeatable)

When the coach asks for a **scouting report** / **team scouting report**:

1. Rebuild from `data/stats/stats.csv` (replace, do not merge exports)
2. Update the printable [`print/team-scouting-report.html`](print/team-scouting-report.html) and the web view [`scouting.html`](scouting.html)
3. Web view: qualitative hitting + pitching boxes (strengths and areas of growth) above sortable tables; **first name + last initial**. Use roster strengths/weaknesses as input only — never mention notes, the roster file, or that a trait is “listed.”

## Scoring sheet (repeatable)

When the coach asks for a **scoring sheet**:

1. Read `data/games/game-XX-lineup.yaml`
2. Write/update `print/game-XX-scoring.html` using `print/scoring-sheet.css`
3. Portrait letter. Batting order from YAML, **first name + last initial**
4. **Pos** column = inning-1 defense (`—` if on the bench)
5. Empty scoring diamonds for innings 1–5, plus 6–7 extras; blank R/H tally columns
6. Scoring key on the **right** (positions 1–9, reach/outs/other shorthand)
7. Line score (Storm + opponent) and pitching log (pre-fill planned pitchers, leave IP/H/R/ER/BB/SO blank)
8. Fill opponent / date / field when known; Storm branding, no solid red/black header fills
