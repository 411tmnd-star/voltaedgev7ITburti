# VoltaEdge v7

VoltaEdge is an IoT electricity intelligence layer designed to turn electrical measurements into understandable explanations and actionable insights.

## Project status

The v7 architecture and recorded design contracts are marked as frozen. The current repository captures recovered project documentation and development-environment evidence.

- **ESP-IDF:** v6.1
- **Target:** ESP32
- **Firmware:** Not yet curated or implementation-verified
- **Hardware:** Not yet integrated or physically verified
- **Calibration, metrology and safety:** Require further validation

An ESP-IDF example build is recorded in checkpoint `CP-000`. It does not establish that VoltaEdge firmware or hardware works.

## Measurement design

The recorded v7 context specifies alternating voltage/current acquisition, I2S0 DMA, frame and timing constraints, and an ESP32 task-ownership model. See the measurement and frozen-contract documents for the recorded details.

## Repository structure

- `docs/` — recovered project overview, measurement timing, procurement notes, frozen contracts, decisions and status
- `engineering/` — development status and engineering evidence
- `scripts/` — reserved for project scripts

## Evidence discipline

Keep planned, implemented, verified, and hardware-verified work distinct. Preserve original specifications and evidence; reconcile recovered context against the canonical frozen v7 specification before treating unresolved details as implementation truth.

## Important limitation

VoltaEdge is not represented here as a certified protection device or a replacement for a utility meter. No safety certification or physical hardware validation is claimed.
