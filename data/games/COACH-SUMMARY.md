# Coach pre-game summary (repeatable task)

Private coach report — not the sideline printable. Use this whenever you want a quick read of who bats where, what each kid plays, and how many innings they sit.

## Trigger phrases

Any of these (or similar):

- “coach summary”
- “pre-game summary”
- “player position report”
- “rebuild the summary”

## Steps for the agent

1. Read the current game plan: `data/games/game-XX-lineup.yaml` (or the active draft in chat if not saved yet).
2. Read season/game stats from `data/stats/stats.csv` when present.
3. Write/overwrite `data/games/game-XX-coach-summary.md` using the structure below.
4. Paste the same content in the chat reply so it’s visible without opening the file.

Also refresh this file whenever the lineup YAML changes in a meaningful way (batting order or defense), unless the coach only asked for the printable.

## Required structure

```markdown
# Storm — Game N Coach Summary

**Opponent:** … · **Date:** … · **Time:** … · **Field:** …
**Pitch plan:** …
**Rules check:** continuous batting · no consecutive sits · …

## Batting order
1. …
…

## By player

| # | Player | Inn 1 | Inn 2 | Inn 3 | Inn 4 | Inn 5 | Sits |
|---|--------|-------|-------|-------|-------|-------|------|
| 1 | … | CF | CF | CF | bench | CF | 1 (4) |
…

## Stats snapshot

Season (or latest export) from `data/stats/stats.csv`. Keep this short — coach view only.

| Player | PA | AVG | OBP | OPS | BB | SO | QAB% | Pitch |
|--------|----|-----|-----|-----|----|----|------|-------|
| … | … | … | … | … | … | … | … | 2.0 IP · 0.00 ERA · 3 K (or —) |

Optional one-line notes under the table (hot bats, pitch limits, missing players).
```

### Column rules

- Position cells: use `P`, `C`, `1B`, `2B`, `3B`, `SS`, `LF`, `CF`, `RF`, or `bench`
- **Sits** column: count of bench innings, with inning numbers in parentheses, e.g. `2 (1, 5)`
- Order **By player** and **Stats snapshot** rows by **batting order**
- Stats columns (keep lean): `PA`, `AVG`, `OBP`, `OPS`, `BB`, `SO`, `QAB%`; **Pitch** only if `IP > 0` (IP · ERA · SO / WHIP as useful), else `—`
- If a rostered player is missing from the CSV, mark `no stats yet`
- Keep it coach-only — no need for print styling, logo, or opponent blanks
