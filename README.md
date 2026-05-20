# Runanywhere Doctor

A single binary CLI + iOS/Android probe app that profiles a device's actual on device inference envelope (memory, sustained tok/s, thermal headroom, ANE/NPU availability) and emits a capability manifest the RunAnywhere control plane can use to route the right model to the right device fleet wide.

![Runanywhere Doctor working dashboard](outputs/project_working.svg)

## Why it exists

RunAnywhere has won "fastest on device LLM+STT+TTS on Apple Silicon" with MetalRT. They have not yet shipped a credible answer to the single question every mobile engineering manager asks before adopting an on device SDK: "Will this model actually fit and run on the median device my user base owns — including the iPhone XS Max and the $200 Android my.

The project is intentionally built as a local replay harness instead of a slide. It creates fixtures, plants realistic failure modes, produces citation-locked evidence, and turns the result into a dashboard a reviewer can inspect without credentials or hosted services.

## What is inside

- Deterministic fixture generation for the company-specific risk surface.
- Strategy code in `src/runanywhere_doctor/strategy.py` with project-specific scoring and visual evidence.
- Citation-locked reports where every decision claim points to a generated evidence ID.
- Two regenerated visual artifacts: `outputs/project_working.svg` and `outputs/evidence_map.svg`.
- A portable demo pack with JSON, CSV, Markdown, HTML, SVG, benchmark, and test artifacts.

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
