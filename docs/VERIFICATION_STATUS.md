# Verification Status and Evidence Boundaries

## Confirmed environment-level evidence (CP-000)

The preserved record says the ESP-IDF development foundation was verified on 2026-10-01:

- ESP-IDF v6.1 at `C:\esp\v6.1\esp-idf`.
- ESP-IDF tag/commit recorded as `v6.1` / `fff9895c`.
- Active Python environment: `C:\Espressif\tools\python\v6.1\venv`.
- Target family: ESP32 / Xtensa.
- Python 3.14.3.
- CMake 4.0.3.
- Ninja 1.12.1.
- ccache 4.12.1.
- The example project at `C:\Users\USER\esp\hello_world` built successfully, producing application, bootloader, and partition binaries.

This proves the recorded development environment and example build were working at that point. It does **not** prove VoltaEdge v7 firmware compiled, ran, or met its measurement requirements.

## Not established by CP-000

The available record does not establish:
- a completed VoltaEdge v7 firmware build;
- assembled or validated hardware;
- mains measurement accuracy;
- phase/delay compensation accuracy;
- energy accounting correctness;
- fault detection or recovery on physical hardware;
- isolation/safety compliance;
- calibrated comparison against reference instruments;
- successful end-to-end field operation.

Mark each claim as verified only after attaching reproducible evidence: exact commit, command, environment, raw output/artifact, test conditions, expected result, observed result, and reviewer/decision.

## Suggested evidence convention

Keep evidence append-only. Each checkpoint should state:
- ID and timestamp;
- source commit and toolchain version;
- test setup and inputs;
- command/procedure;
- expected versus observed result;
- artifacts and checksums where useful;
- pass/fail/inconclusive status;
- limitations and next action.

Do not relabel environment evidence as hardware or firmware evidence.


## Confirmed project-build evidence (CP-001)

The VoltaEdge v7 firmware project built successfully on 2026-10-15 using ESP-IDF v6.1.

- Project: `C:\Users\USER\esp\volta-edge-v7`
- Target: ESP32.
- Build command: `idf.py -C "C:\Users\USER\esp\volta-edge-v7" build`
- Result: `Project build complete.`
- Application binary: `build\VoltaEdge.bin` — 142,288 bytes.
- Application SHA-256: `6D6FC5F4F695DDFBEA6B3CF349D5C767B652186C832AE56C1A604A537C11A0AD`
- Bootloader and partition-table binaries were also generated; their hashes and the build notices are recorded in the CP-001 checkpoint.
- Evidence record: `engineering\evidence\checkpoints\CP-001-voltaedge-firmware-foundation-build.md`

This establishes a successful project build and the recorded build artifacts. It does **not** establish that the firmware was flashed, executed, or validated on physical hardware.

## Still not established by CP-001

- Firmware runtime behavior on an ESP32.
- ADC/I2S/DMA acquisition, frame parsing, buffering, or concurrency correctness.
- Calibration, phase compensation, measurement accuracy, or energy-accounting correctness.
- Fault recovery, electrical isolation, protection behavior, or safety compliance.
- Comparison against calibrated reference instruments or successful field operation.

The build emitted four Kconfig notices concerning boolean defaults. They are documented in CP-001 and should be assessed separately; do not silently modify the installed ESP-IDF source to suppress them.

Verification claims must remain scoped to their evidence. CP-000 documents the environment and separate example build; CP-001 documents the VoltaEdge project build only.
