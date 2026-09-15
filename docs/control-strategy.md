# Control Strategy

## Purpose

Closed-loop control allows a power converter to maintain a commanded electrical quantity despite changes in input voltage, operating point or load.

## Cascaded control structure

The documented development work included voltage and current control. A typical cascaded implementation uses a slower outer voltage loop and a faster inner current loop.

### Outer voltage loop

The voltage controller calculates the current required to correct the output-voltage error:

```text
e_v(k) = V_ref(k) - V_meas(k)
I_ref(k) = PI_voltage(e_v(k))
```

The current reference should be limited to the permitted operating range of the converter.

### Inner current loop

The current controller tracks the limited current reference and generates the modulation command:

```text
e_i(k) = I_ref_limited(k) - I_meas(k)
u(k) = PI_current(e_i(k))
duty(k) = limit(u(k), duty_min, duty_max)
```

For a digitally controlled system, the sampling frequency, PWM frequency, sensor filtering, computation delay and anti-windup method affect stability and dynamic performance.

## Commissioning sequence

1. Confirm sensor polarity and scaling.
2. Verify PWM timing at low voltage with the power stage disabled where possible.
3. Test the current loop with conservative limits.
4. Confirm stable current tracking before closing the outer voltage loop.
5. Increase the voltage reference gradually.
6. Test load steps while monitoring overshoot, settling and current limiting.
7. Verify that protection functions override the controller.

## Parameters intentionally omitted

The available material does not contain verified controller gains, switching frequency, converter ratings or protection thresholds. Adding guessed numbers would make the repository less credible, not more complete.

