# Benchmark audits

Audits of AI benchmarks, checked against the saved logs. Each audit is one page, with the raw evidence it cites next to it.

Site: <https://seungjuchae.github.io/benchmark-audits/> (Korean: `index.ko.html`)

## SDBench

Microsoft [SDBench](https://github.com/microsoft/sdbench), synthetic case 0. Read it at <https://seungjuchae.github.io/benchmark-audits/sdbench/>, or as a PDF: [`sdbench/sdbench-case0-audit.pdf`](sdbench/sdbench-case0-audit.pdf).

```
sdbench/
├── index.html, index.ko.html     the audit in English and Korean: eight findings, each with
│                                 how every setup we tested behaved, plus raw requests and responses
├── sdbench-case0-audit.pdf       the English page as a PDF (.ko.pdf for Korean)
├── gpt5-trajectory/              GPT-5 run: full trajectory JSON
├── astra-max-diagnosis/          Astra max run: trajectory, API calls, run config
├── astra-gatekeeper/replay/      36 saved orders resent to an Astra Gatekeeper
│   └── split-requests/           the 10 refused orders split into 31 requests
└── judge-probes/
    ├── false-intermediate-step/  Judge graded with a planted false explanation
    └── unsupported-complication/ Judge graded with an unsupported added condition
```

Scope: one synthetic case. These are reviews of saved runs, not a benchmark-wide audit or an expert clinical assessment. Links to SDBench source point to commit `304ce96`.

### Changes from the original files

Evidence files are copied unchanged from the SDBench working copy, with three exceptions in `sdbench/astra-max-diagnosis/`. In these, local absolute paths (`C:\Users\…\sdbench\`) were replaced with paths relative to the SDBench checkout (`results/…`). Nothing else changed, but their SHA-256 differs from hashes cited inside other evidence files (e.g. `judge-probes/false-intermediate-step/manifest.json` cites `run_config.json`). The original hashes:

| File | Original SHA-256 |
|---|---|
| `comparison.json` | `513f4e627824d275e1a1df7a50547df7bb5fb0cf0e0381de111e32d9f35860a4` |
| `manifest.json` | `b0505754f901e54c349193540605a170e251f6624dcbe28d61c0589f3b3b257d` |
| `run_config.json` | `0790c144881f1deb3dadc60a23369759b06a905e03c043a7011ecb2f023b67a4` |
