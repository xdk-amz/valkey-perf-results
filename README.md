# Valkey performance results

Benchmark results for Valkey in the vpb-result/1 format, and the static site built from them.

| Path | Holds | Updated by |
|---|---|---|
| `data/official-ci/` | Continuous benchmark runs of valkey-io/valkey unstable | CI on the benchmark repo |
| `data/curated/<owner>/` | Result sets a maintainer curated, such as a PR comparison | Pull request from that owner |
| `data/community/` | Results anyone contributed | Pull request |
| `data/fork/<owner>/<repo>/` | Runs of a fork | Pull request from that fork's owner |
| `.github/workflows/validate.yml` | Schema, fingerprint, location and identifier checks on every push and pull request | This repo |
| `.github/workflows/pages.yml` | Builds the site from `data/` and deploys it to GitHub Pages | This repo |

The views and the validator come from `dashboards/explorer` in [xdk-amz/valkey-perf-benchmark](https://github.com/xdk-amz/valkey-perf-benchmark/tree/explorer), pinned by commit in both workflows. The format is described in its `SCHEMA.md`.

To check and build locally from a checkout of that repo:

```
python3 -m dashboards.explorer check ../valkey-perf-results/data --data-root ../valkey-perf-results/data
python3 -m dashboards.explorer build ../valkey-perf-results/data --out site
```
