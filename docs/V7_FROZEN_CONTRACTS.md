# VoltaEdge v7 — Frozen Contracts and Architecture Locks

**Status:** These items are recorded as frozen design decisions in the preserved project context. This document records their names and boundaries; it does not recreate missing detailed specifications.

## Frozen items

1. Architecture graph.
2. Invariant hierarchy.
3. Ownership model.
4. Stream epoch and frame-sequence model.
5. Parser phase model.
6. Calibration boundary.
7. Window semantics.
8. Energy commit semantics.
9. Fault-recovery path.

These are design locks. Changes should be made only through an explicit, documented decision—not by silently changing behavior during implementation or repository cleanup.

## Runtime platform and acquisition path

The remembered target is an **ESP32-WROOM-32** using ESP-IDF (`esp32` target). Acquisition uses ADC I2S0 with DMA. GPIO18 is the marker; GPIO32 and GPIO33 are the ADC inputs. The ring size is 8. The remembered core split is Core 0 for Wi-Fi stress and Core 1 for the consumer.

## Measurement invariants remembered

- ADC conversion stream: 8,000 conversions/s, alternating I/V.
- Interpreted channel rate: 4,000 voltage samples/s and 4,000 current samples/s.
- Pair rate before delay compensation: 4,000 I/V pairs/s.
- Frame size: 1,280 bytes = 320 conversions = 160 I/V pairs.
- Ten frames: 0.4 s and 1,600 I/V pairs.
- Nominal mains frequency in this specification: 50 Hz.
- One degree at 50 Hz: approximately 55.55 µs.
- I/V sample spacing: 125 µs, equivalent to 2.25° at 50 Hz.
- `M = 4` is a preserved parameter; its precise interpretation must be taken from the canonical v7 specification rather than guessed.

## Do not infer missing details

The context available for this import does not contain the full normative text for:
- exact invariant IDs and precedence;
- stream epoch reset rules and frame-sequence wrap handling;
- parser state transitions and malformed-frame behavior;
- ownership transfer and synchronization primitives;
- calibration equations, sign conventions, and validity ranges;
- window start/end and partial-window rules;
- the exact conditions under which energy is committed or discarded;
- fault classification, recovery ordering, and recovery time limits.

Recover those exact rules from the frozen v7 spec or existing local files. Do not replace them with newly invented rules under the guise of documentation.
