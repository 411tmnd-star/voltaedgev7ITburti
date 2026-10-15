# CP-001 — VoltaEdge Firmware Foundation Build

- Date: 2026-10-15
- Status: BUILD-VERIFIED
- Project: VoltaEdge v7
- Project path: `C:\Users\USER\esp\volta-edge-v7`
- Scope: Build and generated-artifact verification only

## Purpose

Record the first successful ESP-IDF build of the VoltaEdge v7 firmware foundation. This checkpoint supplements CP-000; it does not modify or supersede CP-000.

## Environment

- ESP-IDF: v6.1
- ESP-IDF source commit recorded: `fff9895c`
- Target: ESP32 / Xtensa
- Python: 3.14.3
- CMake: 4.0.3
- Ninja: 1.12.1
- ccache: 4.12.1
- Project Git repository: not initialized; no project source commit is available.

## Build Procedure

Command executed:

```powershell
idf.py -C "C:\Users\USER\esp\volta-edge-v7" build
```

Expected result: ESP-IDF configures and compiles the project and generates the application, bootloader, and partition-table binaries.

Observed result: `Project build complete.` The application binary, bootloader binary, and partition-table binary were generated. The application was reported as 142,288 bytes (`0x22bd0`); the smallest app partition was reported as `0x100000`, with 86% free.

## Generated Artifacts

The following paths, sizes, and SHA-256 hashes were inspected after the build.

| Artifact | Size (bytes) | SHA-256 |
|---|---:|---|
| `build/VoltaEdge.bin` | 142288 | `6D6FC5F4F695DDFBEA6B3CF349D5C767B652186C832AE56C1A604A537C11A0AD` |
| `build/bootloader/bootloader.bin` | 26176 | `DA21C86C5803F58442B0BEEF8BC65516D703FE1A121C599D1B73DC5F906EEC0E` |
| `build/partition_table/partition-table.bin` | 3072 | `7F00B6C042A89B15B0CAC534F82ED988CAF29278FF5700B0C511EB1B5BB7C820` |

## Observed Kconfig Notices

The build emitted the following notices. The build nevertheless completed successfully.

1. `C:/esp/v6.1/esp-idf/components/bt/host/nimble/Kconfig.in:1428: BT_NIMBLE_MESH_PROVISIONER: 'default 0' is not a valid bool value (only 'y' and 'n' are allowed). Value is treated as 'n'.`
2. `C:/esp/v6.1/esp-idf/components/bt/controller/esp32/Kconfig.in:177: BTDM_CTRL_LEGACY_AUTH_VENDOR_EVT_EFF: 'default 0' is not a valid bool value (only 'y' and 'n' are allowed). Value is treated as 'n'.`
3. `C:/esp/v6.1/esp-idf/components/fatfs/Kconfig:240: FATFS_PRINT_LLI: 'default 0' is not a valid bool value (only 'y' and 'n' are allowed). Value is treated as 'n'.`
4. `C:/esp/v6.1/esp-idf/components/fatfs/Kconfig:245: FATFS_PRINT_FLOAT: 'default 0' is not a valid bool value (only 'y' and 'n' are allowed). Value is treated as 'n'.`

These notices are recorded for follow-up; this checkpoint does not establish that they affect firmware behavior.

## Verification Boundaries

Verified by this checkpoint:
- The VoltaEdge v7 project builds successfully with the recorded ESP-IDF environment.
- The three listed binary artifacts exist and their sizes and SHA-256 hashes were inspected.

Not verified by this checkpoint:
- Flashing or startup on a physical ESP32.
- Runtime behavior or hardware integration.
- ADC/I2S/DMA acquisition, GPIO timing, frame parsing, buffering, or concurrency.
- Sensor calibration, phase compensation, metrology, or energy-accounting correctness.
- Fault recovery, electrical isolation, protection behavior, or safety.
- Compliance or suitability as a certified meter or protection device.

The successful separate `hello_world` example build remains environment-level evidence recorded in CP-000; it is not substituted for this project-specific build result.

## Next Actions

1. Reconcile implementation against the complete frozen v7 contracts before implementing acquisition or buffer ownership.
2. Review the Kconfig notices without modifying the installed ESP-IDF source blindly.
3. Perform a separately recorded runtime/hardware verification only when the relevant equipment and test procedure are available and authorized.
4. Preserve this checkpoint as an append-only evidence record.
