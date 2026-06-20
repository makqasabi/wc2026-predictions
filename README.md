# World Cup 2026 — Predictions vs Live Actuals

A mobile-first web page comparing the FMVA group's **FIFA World Cup 2026 Predictor** entries
(from The Telegraph predictor tool) against live tournament results, with an automatic leaderboard.

## What it does

- **Leaderboard** — ranks all 8 entrants by points, updating live as results are entered.
- **Group Stage** — side-by-side comparison of every group table (A–L) vs the actual finishing order; correct positions get a ✓.
- **Knockouts** — each person's champion pick (turns green/red once decided) and full Round-of-32 bracket.
- **Enter Results** — tap-friendly editor to record actual group standings, the 8 best third-place qualifiers, and the champion. Results are saved in the browser (on-device).

## Scoring

| Field | Points |
|---|---|
| Each team in its exact final group position (48 slots) | +3 |
| Each correct best third-place qualifier (8 picks) | +4 |
| Correct World Cup champion | +25 |

Knockout matchups are seeded by each person's own group predictions, so they differ per entrant — the group tables, third-place picks and champion are the comparable, scored fields. Full brackets are shown for reference.

## Entrants

Abdulrahman Othman Tariq · Ahmed Esam · Bader · Mohsen · Naser · Othman Tariq · Tamim · Thamer

## Hosting

Single self-contained `index.html` (no build step, no dependencies — flags load from flagcdn.com).
Deploy to GitHub Pages: push to a repo and enable Pages on the default branch root.

_Predictions sourced from The Telegraph World Cup 2026 Predictor submissions._
