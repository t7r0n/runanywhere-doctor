# Operator Brief: RunAnywhere

RunAnywhere gets a local, deterministic pressure test around runanywhere, fastest, and device. The useful part is the repeatable evidence path from fixture to failure to operator action.

## Highest-leverage checks

- runanywhere evidence replay -> block release until cited evidence is regenerated (runanywhere_coverage, evidence ev_0044).
- apple operator packet -> accept only if decision claims cite fixture evidence (fastest_risk, evidence ev_0099).
- device regression harness -> open a regression issue with trace and benchmark delta (device_precision, evidence ev_0110).
- fastest boundary probe -> route to reviewer with evidence packet (apple_latency, evidence ev_0121).

## What makes this useful

The workflow is intentionally local and deterministic. A reviewer can run the same fixture set, inspect the evidence IDs, open the dashboard, and see exactly why a recommendation passed, went to review, or blocked.
