# Pipeline Watch — Synthetic Data

This bundle contains:
- `landing/` — gzipped CSVs per tenant and hour (≈5k rows each) including some anomalies:
  - `tenantA` (latest hour): higher share of unknown referrers (~35%)
  - `tenantB` (latest hour): latency spike (~2.2× baseline)
  - `tenantC` (older hour): a few bad values (negative or extreme bytes/latency)
  - One **stale** 3-hours-old small file to test freshness & min-size/row rules
- `reference/allowed_countries.csv` — whitelists per tenant
- `reference/baseline_latency.json` — 7-day mean latency per tenant (ms)

Timestamps are generated relative to your current UTC time: 2025-10-03T19:52:31.894688+00:00.

You can use these with the validation script we’ll write next.
