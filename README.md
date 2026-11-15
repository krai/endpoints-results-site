<p align="center">
  <a href="https://krai.github.io/endpoints-results-site/"><img src="assets/banner.svg" alt="KRAI — MLPerf Endpoints v1.0: DeepSeek-V4.1-Flash agentic inference results" width="100%"></a>
</p>

<p align="center">
  <a href="https://krai.github.io/endpoints-results-site/"><img alt="Open the results site" src="https://img.shields.io/badge/results-open%20the%20site-19b1de?style=flat-square&labelColor=021528"></a>
  <a href="https://krai.github.io/endpoints-results-site/data.json"><img alt="Raw data: data.json" src="https://img.shields.io/badge/raw%20data-data.json-118cb1?style=flat-square&labelColor=021528"></a>
  <a href="https://github.com/mlcommons/endpoints"><img alt="Benchmark: MLCommons Endpoints v1.0" src="https://img.shields.io/badge/benchmark-MLCommons%20Endpoints%20v1.0-273747?style=flat-square&labelColor=021528"></a>
</p>

# KRAI MLPerf Endpoints results

Charts and tables of KRAI's [MLCommons Endpoints v1.0](https://github.com/mlcommons/endpoints) submissions for
**DeepSeek-V4.1-Flash** on the **Agentic Inference** benchmark. Each submission covers one system on one date,
measured at several concurrency levels (C32 to C1024 concurrent agent sessions).

**→ [krai.github.io/endpoints-results-site](https://krai.github.io/endpoints-results-site/)**

## What the site shows

| Section | Contents |
|---|---|
| Throughput vs concurrency | Output tokens/s of the whole system at each concurrency |
| Throughput vs interactivity | The trade-off curve: each point is one concurrency; up and to the right is better |
| Throughput relative to a baseline | Each submission as a percentage of a selectable baseline at the same concurrency |
| TTFT p90 vs concurrency | 90th-percentile time to first token, log scale |
| Metric table | Any metric below by submission × concurrency, with the change against the baseline |
| Accuracy | Each point's accuracy against the benchmark's thresholds |
| All points | The full metric set per submission, with its system and software configuration |

Toggle submissions on and off at the top of the page; the selection and the baseline are remembered in your browser.

## Metrics

| Metric | Definition |
|---|---|
| Throughput (TPS) | Output tokens per second across all sessions, measured by the benchmark client |
| Interactivity | End-to-end average output tokens per second seen by one session |
| TTFT | Time to first token of a response |
| TPOT | Time per output token after the first |
| Inline accuracy | Agentic action accuracy scored during the performance run (threshold ≥ 52.36 %) |
| OSL per turn | Mean output length per turn (must lie within 793–970 tokens) |
| SWE-bench | Share of SWE-bench instances resolved, at the points run with accuracy mode (threshold ≥ 96.4 %) |

## Where the numbers come from

Every value is read unmodified from the submission's run folders: the benchmark client's
`performance/result_summary.json`, `scores.json`, `swe_bench_results.json` and `report.txt`, plus the
`system_desc.json` system description. The official status of a submission is the one published by MLCommons.

This repository holds only the generated page: `index.html` and `data.json` on the `gh-pages` branch. They are
rebuilt automatically from KRAI's submission records whenever a submission is added, so do not edit `gh-pages`
by hand.

---

<sub>© KRAI · [krai.ai](https://krai.ai)</sub>
