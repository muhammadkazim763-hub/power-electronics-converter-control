# Verified Component Summary

This summary is derived from the project bill of materials dated 11 October 2022. It describes the main functional blocks without publishing the complete purchasing workbook.

## Power stage

| Function | Manufacturer | Part | Verified specification | Quantity |
| --- | --- | --- | --- | ---: |
| Three-phase SiC inverter power module | Danfoss Silicon Power | MiniPack1b | 1,200 V, 30 A | 1 |
| Isolated gate driver | onsemi | NCV57001DWR2G | High-current driver with internal galvanic isolation | 6 |

The six isolated gate-driver channels are consistent with a conventional three-phase, two-level bridge containing six actively controlled switching positions.

## Voltage and current measurement

| Function | Manufacturer | Part | Verified specification | Quantity |
| --- | --- | --- | --- | ---: |
| Current sensing | LEM | LESR 25-NP | Isolated current sensor; BOM lists -85 A to +85 A measurement range | 3 |
| Voltage sensing | LEM | LV25-P | Hall-effect voltage transducer | 1 |
| High-speed signal conditioning | Analog Devices | LT1809 | Rail-to-rail high-speed operational amplifier | 3 |
| Precision signal conditioning | Texas Instruments | OPA211AIDGKT | Low-noise precision operational amplifier | 1 |
| Threshold comparison | Texas Instruments | TLV9032QDRQ1 | Dual push-pull precision comparator | 3 |

These devices support closed-loop current and voltage measurement, analogue conditioning and protection-threshold detection.

## Auxiliary power supplies

| Function | Manufacturer | Part | Verified specification | Quantity |
| --- | --- | --- | --- | ---: |
| Isolated gate-driver supply | Murata | NMK0512SC | 5 V input, +12 V/-12 V dual output, 2 W | 6 |
| Isolated auxiliary DC/DC supply | Traco Power | THL 25-2411 | 25 W, 2:1 input-range module | 1 |
| Adjustable linear regulation | onsemi | LM317 family | 100 mA and 500 mA variants | 7 total |

The isolated dual-output modules provide a separate bipolar auxiliary supply for each gate-driver channel.

## DC link, filtering and protection

| Category | Verified items from BOM |
| --- | --- |
| DC-link capacitance | Six 470 uF / 400 V electrolytic capacitors and four 50 uF / 450 V polypropylene film capacitors |
| High-frequency capacitance | 500 V C0G ceramic capacitors and 2 kV ceramic capacitors |
| Surge protection | 550 VAC / 745 VDC MOV with 910 V varistor voltage and 4.5 kA surge rating |
| Filtering | 12 uH inductors, common-mode chokes and a 2.2 uH high-current inductor |
| Semiconductor protection | Zener, Schottky and transient-voltage-suppression devices |
| Isolation and logic | ISO721 digital isolators, Schmitt-trigger inverters, NOR/AND logic and flip-flop logic |

## What the BOM proves

The BOM verifies that the platform included:

- A high-voltage three-phase SiC inverter power stage
- Six isolated switching channels
- Three-phase current sensing and DC-link voltage sensing
- Isolated gate-driver power supplies
- Analogue signal conditioning and comparator-based monitoring
- DC-link energy storage, filtering and surge protection

It does **not** provide verified switching frequency, controller gains, modulation strategy, measured efficiency or completed test results. Those values are not claimed in this portfolio.
