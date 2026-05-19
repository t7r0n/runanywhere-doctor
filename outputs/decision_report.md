# Decision Report: Runanywhere Doctor

A single binary CLI + iOS/Android probe app that profiles a device's actual on device inference envelope (memory, sustained tok/s, thermal headroom, ANE/NPU availability) and emits a capability manifest the RunAnywhere control plane can use to route the right model to the right device fleet wide.

## Evidence-Grounded Findings

CLAIM: apple policy boundary should `block release until replay is understood` because blocks=2 reviews=3 mean_severity=1.708. [EVID: ev_0099]
CLAIM: device failure replay should `block release until replay is understood` because blocks=2 reviews=4 mean_severity=3.333. [EVID: ev_0044]
CLAIM: fastest gap should `block release until replay is understood` because blocks=3 reviews=2 mean_severity=3.333. [EVID: ev_0143]
CLAIM: fastest reviewer handoff should `block release until replay is understood` because blocks=2 reviews=4 mean_severity=2.583. [EVID: ev_0121]
CLAIM: runanywhere drift should `block release until replay is understood` because blocks=2 reviews=3 mean_severity=2.5. [EVID: ev_0088]
CLAIM: runanywhere evidence recall should `block release until replay is understood` because blocks=3 reviews=3 mean_severity=1.875. [EVID: ev_0000]
