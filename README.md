# Valkey performance results

Benchmark results for Valkey, one `vpb-result` file per run, and the static site built from them.

| Path | Holds | Updated by |
|---|---|---|
| `data/official-ci/<run id>.json` | Continuous benchmark runs of valkey-io/valkey unstable | CI on the benchmark repo |
| `data/curated/<owner>/<run id>.json` | Runs a maintainer curated, such as the two builds of a PR comparison | Pull request from that owner |
| `data/community/<run id>.json` | Runs anyone contributed | Pull request |
| `data/fork/<owner>/<repo>/<run id>.json` | Runs of a fork | Pull request from that fork's owner |
| `metrics.json` | Every metric's name, unit, better direction and bar | This repo |
| `.github/workflows/validate.yml` | Format, fingerprint, location and identifier checks on every push and pull request | This repo |
| `.github/workflows/pages.yml` | Builds the site from `data/` and deploys it to GitHub Pages | This repo |

The views and the validator come from `dashboards/explorer` in [xdk-amz/valkey-perf-benchmark](https://github.com/xdk-amz/valkey-perf-benchmark/tree/explorer), pinned by commit in both workflows. The format is described in its `SCHEMA.md`.

To check and build locally from a checkout of that repo:

```
python3 -m dashboards.explorer check ../valkey-perf-results/data --data-root ../valkey-perf-results/data --metrics ../valkey-perf-results/metrics.json
python3 -m dashboards.explorer build ../valkey-perf-results/data --metrics ../valkey-perf-results/metrics.json --out site
```
