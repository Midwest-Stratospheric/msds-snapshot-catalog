# MSDS Snapshot Catalog

**Permanent, append-only catalog of open-tier scientific snapshots** from:

| Source repo | What is archived |
|-------------|------------------|
| [Unified-Open-Global-Weather](https://github.com/Midwest-Stratospheric/Unified-Open-Global-Weather) | Research summary, science package, scorecard, coverage, FAIR card, anomaly report, reports, charts |
| [aerostratospheric-defense-gir](https://github.com/Midwest-Stratospheric/aerostratospheric-defense-gir) | Manifest, exec summary, scientific scorecard, change detection, coverage, FAIR card |

## Design

- Operational repos keep overwriting `data/latest/` for convenience.
- **This catalog never erases history.** Each UTC day gets its own folder:
  - `catalog/uogw/YYYY-MM-DD/`
  - `catalog/gir/YYYY-MM-DD/`
- Index: `index/latest.json` and `index/YYYY.json`
- Daily Action **pulls** from the public source repos and **only adds** dated trees.

## Layout

```
catalog/
  uogw/YYYY-MM-DD/
  gir/YYYY-MM-DD/
index/
  latest.json
  2026.json
```

## Automation

- Workflow: [Ingest Snapshots](https://github.com/Midwest-Stratospheric/msds-snapshot-catalog/actions/workflows/ingest-snapshots.yml)
- Schedule: **10:00 UTC** daily
- Manual dispatch supported

## Policy

- Open-tier / public data only
- Research screening — not an official product
- **No automatic deletion** of prior dated folders
- Upstream licenses stay with source agencies and original repos

## Curator

Midwest Stratospheric Data Systems / Aerostratospheric  
https://midwestsds.com/
