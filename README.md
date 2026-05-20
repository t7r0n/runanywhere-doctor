# Offline Deployment Diagnostics Doctor

A single binary CLI + iOS/Android probe app that profiles a device's actual on device inference envelope (memory, sustained tok/s, thermal headroom, ANE/NPU availability) and emits a capability manifest the Offline Deployment Diagnostics control plane can use to route the right model to the right device fleet wide.

![Offline Deployment Diagnostics Doctor working dashboard](outputs/project_working.svg)

## Why it exists

Offline Deployment Diagnostics has won "fastest on device LLM+STT+TTS on Apple Silicon" with MetalRT. They have not yet shipped a credible answer to the single question every mobile engineering manager asks before adopting an on device SDK: "Will this model actually fit and run on the median device my user base owns — including the iPhone XS Max and the $200 Android my.

The project is intentionally built as a local replay harness instead of a slide. It creates fixtures, plants realistic failure modes, produces citation-locked evidence, and turns the result into a dashboard a reviewer can inspect without credentials or hosted services.

## What is inside

- Deterministic fixture generation for the company-specific risk surface.
- Strategy code in `src/Offline Deployment Diagnostics_doctor/strategy.py` with project-specific scoring and visual evidence.
- Citation-locked reports where every decision claim points to a generated evidence ID.
- Two regenerated visual artifacts: `outputs/project_working.svg` and `outputs/evidence_map.svg`.
- A portable demo pack with JSON, CSV, Markdown, HTML, SVG, benchmark, and test artifacts.

![Offline Deployment Diagnostics Doctor evidence map](outputs/evidence_map.svg)

## Signals it measures

- `Offline Deployment Diagnostics coverage`
- `fastest risk`
- `device precision`
- `apple latency`

## Failure modes it plants

- Offline Deployment Diagnostics drift
- fastest gap
- device misroute
- apple blindspot

## Run it locally

```bash
uv sync
uv run Offline Deployment Diagnostics-doctor all
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

## Boundary

Everything runs locally against synthetic fixtures. There are no credentials, no customer records, no outreach files, and no hosted API dependency.
