# Stryker Vehicles Predictive Tool - Backend MVP

This build converts the previous hard-coded frontend MVP into a working full-stack demo with:

- a persistent Node/Express backend
- seeded vehicle-only GCSS-Army example data
- shop stock persisted in `server/data/db.json`
- training event creation using Location, auto-distance, vehicle count, and date range
- algorithm predictions saved separately from human-adjusted predictions
- actual result entry and separate algorithm-vs-human error tracking
- first-5-row shop stock view on the home page with Show All toggle

## Run locally

```bash
npm install
npm run seed
npm run dev
```

- Frontend: http://localhost:5173
- API: http://localhost:3001

## Build frontend

```bash
npm run build
```

## Reset seeded data

```bash
npm run seed
```

This recreates `server/data/db.json` from the included example spreadsheets in `seed-data/`.

## Included example data

- `seed-data/MATSIT Vehicles Only.XLSX`
- `seed-data/SSL Example Vehicles Only.xlsx`
- `seed-data/Demand Analysis Vehicles.XLSX`
- `seed-data/ZRRR 24 Oct Vehicles Only.xlsx`

## Notes

- Destructive delete and undo are intentionally preserved as non-destructive UI actions in this build.
- Manual actual-results entry is functional; spreadsheet-based actual-results import is not included.
- Reorder recommendations use a Bayesian-style MVP heuristic that considers quarter context, prior matching quarter, lead time, and demand signals from the example datasets.
