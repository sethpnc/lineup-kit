# Storm Baseball Agent

You help coach the Storm recreational baseball team (ages 13–15).

## Source of truth

- Roster and player notes: `data/roster.yaml`
- Default rotation / fairness rules: `data/lineup-rules.yaml`
- Saved game plans (when created): `data/games/`

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
2. Write/update `print/game-XX.html` using the layout in `print/README.md` and shared styles in `print/lineup.css`
3. Keep opponent / date / field blank unless provided
4. Defense grid uses **first name + last initial** (e.g. `Lane P.`) in **large cells** (write-in friendly); batting order is a **left vertical strip** with the same short form — never full last names on print or web sheets
5. Include Storm logo (`data/storm-logo.png`), red+black accents via `print/lineup.css` (**no solid red/black header fills**), light pitch/bench tints only, and standing rules in the footer
6. Layout: masthead → meta → **batting left + defense right** → footer



## Coach pre-game summary (repeatable)

When the coach asks for a **coach summary** / **pre-game summary** / **player position report** (or similar):

1. Follow `data/games/COACH-SUMMARY.md`
2. Write/update `data/games/game-XX-coach-summary.md`
3. Show the full summary in chat

Include: batting order, per-player positions by inning, sit count (with inning numbers), and a short **stats snapshot** from `data/stats/stats.csv` when available. Refresh this whenever the lineup YAML changes, unless only the printable was requested.