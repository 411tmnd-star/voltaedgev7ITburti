# VoltaEdge v7 — Context Addition (2026-10-15)

This folder is an **additive documentation import** assembled from the user's preserved VoltaEdge project context. It is deliberately isolated so it can be copied into `C:\Users\USER\esp\volta-edge-v7` without overwriting existing project files.

## Documents

- `PROJECT_OVERVIEW.md` — purpose, boundaries, user-facing loop, and example.
- `V7_FROZEN_CONTRACTS.md` — v7 design decisions recorded as frozen.
- `MEASUREMENT_TIMING.md` — sampling, framing, timing, and ESP32 ownership constraints.
- `PROCUREMENT.md` — currently remembered procurement specifications and indicative prices.
- `VERIFICATION_STATUS.md` — what is verified versus not verified.
- `DECISIONS_AND_OPEN_ITEMS.md` — preservation rules and missing source detail.
- `V7-STATUS.yaml` — compact machine-readable status snapshot.

## Evidence discipline

This is a context recovery package, **not proof that firmware, hardware, metrology, or protection behavior works**. The environment-level build evidence is described separately from v7 implementation evidence. Values below are preserved from the project context and should be reconciled against the original frozen v7 specification and actual files before being treated as implementation truth.

## Safe integration

1. Inspect the existing local project first.
2. Copy this folder into the repository as `engineering/context_import_2026-10-15/` (or another non-conflicting path).
3. Review it against the canonical v7 spec; do not replace existing files automatically.
4. Commit and push only after checking the staged file list and excluding secrets, build outputs, and unrelated ESP-IDF files.
