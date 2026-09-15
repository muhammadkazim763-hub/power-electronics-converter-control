# Hardware Assembly and Testing

## PCB preparation

- Confirm component identity, package and polarity against the schematic and bill of materials.
- Inspect the bare board for visible damage or contamination.
- Populate low-profile components before larger connectors and power components.
- Apply controlled soldering temperature and minimise unnecessary thermal exposure.
- Inspect joints for bridging, insufficient wetting, lifted pads and incorrect orientation.

## Pre-power checks

- Inspect the board under adequate lighting and magnification.
- Check resistance between each supply rail and ground.
- Confirm continuity across intended connections.
- Verify isolation between power and control domains where required.
- Check auxiliary-supply input polarity.
- Confirm that gate-drive outputs are inactive before enabling the power stage.

## Staged commissioning

The safest useful workflow is to energise the design in sections:

1. Auxiliary power supplies
2. References and sensing circuits
3. Controller and PWM outputs
4. Gate drivers without full bus voltage
5. Power stage at reduced voltage and current limit
6. Closed-loop operation under a controlled load

## Measurement focus

- Supply-rail values and ripple
- Sensor offsets and scaling
- PWM frequency and duty cycle
- Gate-drive amplitude and timing
- Output voltage regulation
- Current tracking and limiting
- Transient response during reference or load changes
- Abnormal heating, noise or oscillation

## Fault-isolation approach

Start from the observed symptom and divide the system into power, sensing, control, gate-drive and load sections. Compare each section with its expected state, identify the first incorrect node, correct the cause and repeat the complete verification sequence.

