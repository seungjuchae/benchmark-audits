# Benchmark audits

Audits of AI benchmarks, checked against the saved logs. Each page keeps the evidence it cites next to it.

## SDBench

Microsoft [SDBench](https://github.com/microsoft/sdbench), synthetic case 0. Read it at <https://seungjuchae.github.io/benchmark-audits/sdbench/>, or as a PDF: [`sdbench/sdbench-case0-audit.pdf`](sdbench/sdbench-case0-audit.pdf).

```
sdbench/
├── index.html                    main page: case 0 audit, four findings from the GPT-5 run
├── materials.html                list of all materials
├── gpt5-trajectory/              GPT-5 trajectory audit (en.html, ko.html) + trajectory JSON
├── astra-gatekeeper/
│   ├── review.html               Astra Gatekeeper review
│   └── replay/                   GPT-5 vs Astra Gatekeeper replay (36 saved requests)
│       └── split-requests/       10 refused bundles split into 31 requests
├── astra-max-diagnosis/          GPT-5 vs Astra max diagnostic runs
├── judge-probes/
│   ├── unsupported-complication/ Judge A/B: unsupported complication added
│   └── false-intermediate-step/  Judge A/C: false intermediate explanation
├── daniel-brief/                 summary brief
├── cost-leaderboard.html         estimated cost: physician path vs GPT-5
└── sdbench-case0-audit.pdf       main page as PDF, all sections expanded
```

Scope: one synthetic case. These are reviews of saved runs, not a benchmark-wide audit or an expert clinical assessment. Links to SDBench source point to commit `304ce96`.

### Changes from the original files

Files are copied unchanged from the SDBench working copy, with three exceptions in `sdbench/astra-max-diagnosis/`. In these, local absolute paths (`C:\Users\…\sdbench\`) were replaced with paths relative to the SDBench checkout (`results/…`). Nothing else changed. Their SHA-256 therefore differs from hashes cited elsewhere (e.g. the summary brief cites `run_config.json`). The original hashes:

| File | Original SHA-256 |
|---|---|
| `comparison.json` | `513f4e627824d275e1a1df7a50547df7bb5fb0cf0e0381de111e32d9f35860a4` |
| `manifest.json` | `b0505754f901e54c349193540605a170e251f6624dcbe28d61c0589f3b3b257d` |
| `run_config.json` | `0790c144881f1deb3dadc60a23369759b06a905e03c043a7011ecb2f023b67a4` |

Links between pages were rewritten for the new layout, and `cost-leaderboard.html` was wrapped in a page shell (charset, styles) around its original content.
