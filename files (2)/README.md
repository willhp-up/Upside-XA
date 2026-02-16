# UPSIDE — Model Analyst Command Centre

Personal PM platform for managing AI stock-picking models across teams.

## Architecture

```
YOU (PM)
├── Team: Travel
│   └── Tig (K-shape travel model) ← built-in
├── Team: Defence
│   └── [Import or build models]
├── Team: Tech & Robotics
│   └── [Import or build models]
└── Export Centre → CSV / JSON → XA-Coach
```

**Models** are the analysts. You group them into **Teams**. Each model has its own conviction list, scorecard, and CSV import/export. The **Macro Environment** sets global scoring weights that apply across all models.

## Key Views

| View | What it does |
|------|-------------|
| **Overview** | Stats across all models and teams |
| **Team drilldown** | Click any team to see its models and top picks |
| **Model drilldown** | Conviction list, scorecard, CSV import for each model |
| **Macro Environment** | Set/adjust global macro driver weights |
| **Export Centre** | Export all, by team, or single model as CSV or JSON |

## Model Types

- **Built-in**: Created directly in the dashboard. Add tickers, score them, write theses.
- **Imported**: Fed via CSV. Paste or upload a CSV to populate a model's conviction list.

## CSV Format

```
ticker, bbg_ticker, name, sector, verdict, tier, model, thesis,
px_last, chg_ytd, mkt_cap, pe_fwd, ev_ebitda, net_debt_ebitda,
oper_margin, fcf_yield, [macro_driver_ids...]
```

## Deploy to GitHub Pages

1. Push `index.html` and `.nojekyll` to your repo
2. Settings → Pages → Deploy from branch → `main` → `/ (root)` → Save
3. Access at `https://username.github.io/reponame/`

## Data Storage

All data lives in your browser's `localStorage`. Use JSON export for backups.
No server, no auth, no external dependencies beyond CDN-loaded React.
