# World Cup 2026 — Predictions vs Live Actuals

A mobile-first web page comparing the FMVA group's **FIFA World Cup 2026 Predictor** entries
(from The Telegraph predictor tool) against live tournament results, with an automatic leaderboard.

## What it does

- **Leaderboard** — two boards: **Predictors** (ranked by total points) and **Accuracy** (ranked by % of decided picks correct — fair for late joiners who only predicted some games). Both include the original 11 and any new joiners.
- **Match Picks** — every group game with its real scoreline, and each person's predicted winner per match (green ✓ correct / red ✗ wrong / grey not yet played). Match picks are derived from each person's group ranking (the higher-ranked team is their predicted winner of that head-to-head).
- **Group Tables** — live, auto-computed standings (from results) vs each person's predicted finishing order.
- **Knockouts** — each person's champion pick (turns green/red once decided) and full Round-of-32 bracket.
- **Results** — tap-friendly editor with the **real group results pre-loaded**; edit any scoreline (and the champion) as the tournament progresses. Edits are saved on-device and override the defaults; "Reset to official results" restores them.

Real group-stage results are baked in (sourced from Wikipedia) and standings/third-place qualifiers are computed automatically.

## Scoring

| Field | Points | When |
|---|---|---|
| Correct match result (per group game) | +3 | live |
| Each team in its exact final group position | +3 | locks when a group finishes all 6 games |
| Each correct best third-place qualifier | +4 | end of group stage |
| Correct World Cup champion | +25 | final |

Knockout matchups are seeded by each person's own group predictions, so they differ per entrant — match picks, group tables, third-place picks and champion are the comparable, scored fields. Full brackets are shown for reference.

## Two leagues (separate links)

The site splits into two friend groups via a URL parameter (one shared file, so results stay in sync):

- **League 1** — `?g=1` — Tamim, Mohsen, Bader, Naser, Thamer, Ahmed Esam
- **League 2** — `?g=2` — Othman Tariq, Abdulrahman Othman Tariq, Mohammad Saad, Salman Othman Tariq, Tariq Othman Tariq, Mohsen

Live links:
- League 1 → https://makqasabi.github.io/wc2026-predictions/?g=1
- League 2 → https://makqasabi.github.io/wc2026-predictions/?g=2

The bare URL (no `?g=`) shows a league chooser. Mohsen appears in both.

### Join links (for new guessers)

New people can predict the **upcoming (not-yet-played) matches** + champion and land on the leaderboard:

- Join League 1 → https://makqasabi.github.io/wc2026-predictions/?g=1&guess
- Join League 2 → https://makqasabi.github.io/wc2026-predictions/?g=2&guess

A guest predicts the **whole tournament, progressively**:
1. Pick the winners of every remaining group game (+3 each once played).
2. Those picks (plus real results so far) decide each group's final table — top 2 + best 8 third-placed advance.
3. The **Round of 32 is auto-seeded** from those standings using the official WC2026 bracket template (incl. third-place allocation).
4. Pick knockout winners round by round — each round's matchups come from the previous round's picks — through to the **final, which sets their champion** (+25).

Their picks save on-device and they appear as a **guest** on that league's board. "Copy my shareable link" produces a `#join=…` link encoding the full bracket — when anyone opens it, that guest is added to their board too. (No backend: this is the static-hosting way to let guests join. A live shared board would need a database, e.g. Firebase.)

## Entrants (all)

Abdulrahman Othman Tariq · Ahmed Esam · Bader · Mohammad Saad · Mohsen · Naser · Othman Tariq · Salman Othman Tariq · Tamim · Tariq Othman Tariq · Thamer

## Hosting

Single self-contained `index.html` (no build step, no dependencies — flags load from flagcdn.com).
Deploy to GitHub Pages: push to a repo and enable Pages on the default branch root.

_Predictions sourced from The Telegraph World Cup 2026 Predictor submissions._
