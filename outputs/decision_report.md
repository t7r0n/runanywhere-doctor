# Decision Report: Offline Deployment Diagnostics

A single binary CLI + iOS/Android probe app that profiles a device's actual on device inference envelope (memory, sustained tok/s, thermal headroom, ANE/NPU availability) and emits a capability manifest the Offline Deployment Diagnostics control plane can use to route the right model to the right device fleet wide.

## Evidence-Grounded Findings

CLAIM: claim regression harness should `open a regression issue with trace and benchmark delta` because blocks=3 reviews=5 mean_severity=2.528. [EVID: ev_0110]
CLAIM: evidence replay should `block release until cited evidence is regenerated` because blocks=4 reviews=5 mean_severity=2.611. [EVID: ev_0088]
CLAIM: handoff boundary probe should `route to reviewer with evidence packet` because blocks=3 reviews=4 mean_severity=2.528. [EVID: ev_0077]
CLAIM: review operator packet should `accept only if decision claims cite fixture evidence` because blocks=4 reviews=5 mean_severity=2.556. [EVID: ev_0099]
