# VoltaEdge Procurement Notes

**Scope:** Remembered procurement snapshot. Prices are indicative historical notes, not verified live quotes. Confirm exact part, isolation rating, module variant, availability, and price before purchasing.

## Procurement preference

The recorded preference is to check Port Harcourt Hub360 first and import only if a compliant option is unavailable locally. Do not substitute parts solely because a similarly named module appears cheaper.

## Remembered items

| Item | Remembered price | Notes |
|---|---:|---|
| Core kit | ₦38,550 | Contents must be checked against the original bill of materials. |
| ADuM1201 | ₦4,000 | Digital isolator; confirm package and module implementation. |
| B0505LS-1W | ₦1,600 | Isolated DC/DC converter; confirm exact variant and ratings. |
| MAX485 | ₦220 | RS-485 transceiver; confirm part/module and electrical interface. |
| HWCT-5A/5mA | ₦1,600 | Current-transformer item; confirm exact model and ratio. |
| ZMPT101B | ₦4,500 | Voltage transformer module; confirm module design and safety characteristics. |

## Remembered analog front-end assumptions

- ADC bias: 1.65 V.
- HWCT current transformer: 1000:1 with a 220 Ω burden resistor.
- ZMPT101B: remembered target of 1 Vrms at 240 Vac.

These are design notes, not a safety approval or validated metrology result. Validate isolation, creepage/clearance, burden power, input range, clamping, analog filtering, ADC limits, and calibration before connecting to mains. Never treat a low-cost module's marketing description as proof of mains-safety compliance.

## Procurement evidence still needed

- Dated supplier links/screenshots and actual prices.
- Exact part numbers and module revisions.
- Electrical ratings and isolation documentation.
- BOM quantities and total including shipping.
- Explicit acceptance/rejection record for any substitute.
