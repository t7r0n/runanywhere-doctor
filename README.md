# Runanywhere Doctor

A single binary CLI + iOS/Android probe app that profiles a device's actual on device inference envelope (memory, sustained tok/s, thermal headroom, ANE/NPU availability) and emits a capability manifest the RunAnywhere control plane can use to route the right model to the right device fleet wide.

## Why This Exists

RunAnywhere has won "fastest on device LLM+STT+TTS on Apple Silicon" with MetalRT. They have not yet shipped a credible answer to the single question every mobile engineering manager asks before adopting an on device SDK: "Will this model actually fit and run on the median device my user base owns - including the iPhone XS Max and the $200 Android my users in Lagos use?" Issue 480 (crash on iPhone XS Max during model load) is the literal materialized version of that fear.

## What It Builds

- Replays synthetic `runanywhere` and `fastest` cases against the project's evidence rules.
- Scores `runanywhere_coverage`, `fastest_risk`, and `device_precision` so regressions are visible in CSV and JSON.
- Plants `runanywhere drift` and `fastest gap` failures as negative controls.
- Writes citation-locked decision claims; unsupported claims fail verification.
- Exports a review dashboard and demo pack for `runanywhere-doctor` without hosted services.

## Local Run

```bash
uv sync
uv run runanywhere-doctor all
uv run pytest -q
uv run ruff check .
```

## Outputs

- `outputs/analysis.json`
- `outputs/scenario_report.csv`
- `outputs/decision_report.md`
- `outputs/evidence_packet.md`
- `outputs/dashboard.html`
- `outputs/demo_pack.zip`

## Sources

- https://github.com/RunanywhereAI/runanywhere-sdks
- https://github.com/RunanywhereAI/runanywhere-sdks/issues
- https://huggingface.co/blog/runanywhere/metalrt-fastest-inference-apple-silicon
- https://huggingface.co/blog/runanywhere/runanywhere-intro
- https://x.com/sanchitmonga22/status/2030923381181223384
- https://www.foundersbrief.vc/p/runanywhere
- https://www.ycombinator.com/companies/runanywhere
- https://www.producthunt.com/products/runanywhere
- https://www.runanywhere.ai/blog/how-to-run-ai-models-locally-2026

## Boundary

This repository uses synthetic fixtures only. It has no credentials, no customer data, no outreach data, and no dependency on a hosted API.
