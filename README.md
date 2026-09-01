# Basketball Game Analysis (Freelance)

Freelance data analysis project for an amateur basketball team ("Sharks"): cleans raw box-score exports from multiple games, builds per-player and per-team statistics, and produces comparison visualizations (radar charts, bar charts) used to prepare a scouting/performance report.

## What it does

- **Data cleaning** (`Sharks_Analysis.ipynb`): reads per-game, per-team box-score CSVs (points, rebounds, assists, steals, blocks, turnovers, shooting splits, fouls, etc.), standardizes column names, and tags each row with match metadata (team, rival, date, location).
- **Team-level aggregation**: sums player stats up to team totals per game and recomputes shooting percentages (3PT/2PT/FT) from the aggregated makes/attempts.
- **Comparative visualization**: builds radar charts (Plotly) and bar charts (matplotlib/seaborn, saved under `statsPerPlayer/` and `statsPerTeam/`) comparing Sharks vs. each opponent (Cam, SFA, SFB) across offensive, defensive, and shooting metrics.
- **Play-by-play exploration** (`PBP.ipynb`): loads the raw play-by-play feed for a game as a starting point for event-level analysis.
- **Report**: findings were consolidated into `docs/sharksAnalysis.pdf`.

## Tech stack

Python, pandas, Plotly, matplotlib.

## Project structure

```
Sharks_Analysis.ipynb   # Main cleaning + team/player stats + radar & bar charts
PBP.ipynb               # Play-by-play data exploration
data/                   # Raw per-game box-score CSVs (Sharks vs Cam / SFA / SFB)
statsPerPlayer/         # Generated player comparison charts
statsPerTeam/           # Generated team comparison charts
docs/sharksAnalysis.pdf # Final report
```

## How to run

```bash
pip install pandas plotly matplotlib seaborn
```

Open `Sharks_Analysis.ipynb`; note the data-loading cells originally used absolute local paths and should be pointed at the CSVs under `data/` instead. Run top to bottom to reproduce the cleaned datasets and charts.
