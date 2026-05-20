# Runanywhere Doctor

A single binary CLI + iOS/Android probe app that profiles a device's actual on device inference envelope (memory, sustained tok/s, thermal headroom, ANE/NPU availability) and emits a capability manifest the RunAnywhere control plane can use to route the right model to the right device fleet wide.

![Runanywhere Doctor working dashboard](outputs/project_working.svg)

## Why it exists

RunAnywhere has won "fastest on device LLM+STT+TTS on Apple Silicon" with MetalRT.

Most internal demos stop at a pretty chart. This repository is built around the harder part: a repeatable path from fixture, to failure, to evidence, to the operator action a serious team would actually trust.

## What is inside

- A deterministic replay harness tuned around runanywhere, fastest, and device.
- Company-specific strategy code in `src/runanywhere_doctor/strategy.py`, not just README-level customization.
- Citation-locked reports where every decision claim has to point back to a generated evidence ID.
- Two visual artifacts generated from the latest run: `outputs/project_working.svg` and `outputs/evidence_map.svg`.
- A portable demo pack with JSON, CSV, Markdown, HTML, SVG, and benchmark artifacts.

![Runanywhere Doctor evidence map](outputs/evidence_map.svg)

## Signals it measures

- `runanywhere coverage`
- `fastest risk`
- `device precision`
- `apple latency`

## Failure modes it plants

- runanywhere drift
- fastest gap
- device misroute
- apple blindspot

## Run it locally

```bash
uv sync
uv run runanywhere-doctor all
uv run pytest -q
uv run ruff check .
```

## Outputs worth opening

- `outputs/dashboard.html`
- `outputs/project_working.svg`
- `outputs/evidence_map.svg`
- `outputs/operator_brief.md`
- `outputs/decision_report.md`
- `outputs/strategy_model.json`
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

Everything runs locally against synthetic fixtures. There are no credentials, no customer records, no outreach files, and no hosted API dependency.
