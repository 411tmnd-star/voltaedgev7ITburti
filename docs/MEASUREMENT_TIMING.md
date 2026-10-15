# Measurement and Timing Reference

This page preserves the known acquisition and timing values for review against the frozen v7 specification.

## Sampling and framing

| Item | Preserved value |
|---|---:|
| Aggregate conversion rate | 8,000 conversions/s |
| Channel order | Alternating voltage/current (V/I) |
| Voltage sample rate | 4,000 samples/s |
| Current sample rate | 4,000 samples/s |
| I/V pair rate before delay compensation | 4,000 pairs/s |
| Frame size | 1,280 bytes |
| Conversions per frame | 320 |
| I/V pairs per frame | 160 |
| Frames in the stated example | 10 |
| Duration of 10 frames | 0.4 s |
| Pairs in 10 frames | 1,600 |
| Nominal mains frequency | 50 Hz |
| Time per mains cycle | 20 ms |
| Time corresponding to 1° at 50 Hz | about 55.55 µs |
| Remembered voltage/current sample spacing | 125 µs |
| Phase represented by 125 µs at 50 Hz | 2.25° |
| Parameter `M` | 4 (meaning must be verified in canonical spec) |

The arithmetic is internally consistent for the stated nominal rate: 320 conversions ÷ 8,000 conversions/s = 0.04 s per frame; ten frames are 0.4 s. The 125 µs spacing is a remembered design value and should not be mistaken for a calibrated channel-delay result.

## Platform and ownership

- MCU/module: ESP32-WROOM-32.
- ESP-IDF target: `esp32`.
- ADC acquisition: I2S0 + DMA.
- Marker GPIO: GPIO18.
- ADC GPIOs: GPIO32 and GPIO33.
- Ring size: 8.
- Core allocation noted in the design: Core 0 handles Wi-Fi stress; Core 1 runs the consumer.

The precise pin-to-signal assignment, ADC attenuation/width, analog conditioning, DMA descriptor ownership, overflow behavior, and task synchronization must be verified from the canonical v7 files. Do not infer them from the GPIO list alone.

## Calibration boundary

Calibration is a frozen architectural boundary. Keep raw acquisition, calibration, delay compensation, and downstream measurement interpretation distinct according to the canonical design. This note does not specify calibration coefficients or an approved calibration procedure.

## Energy windows and commit

Window semantics and energy commit semantics are frozen. Preserve the existing contract when implementing or documenting integration. This context package does not define the authoritative start/end conditions, persistence format, rounding policy, or recovery behavior; retrieve those from the canonical specification.
