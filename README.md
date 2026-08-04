# Fluoplasmic-Fields

## RF Shield / Indium Skin Simulator Baseline

This repository currently contains no application code, so the simulator baseline is defined here for the next implementation step.

### Plasma crossover formulation

Use the electron plasma frequency to determine when the gas layer behaves as a field-dominated plasma:

\[
\omega_p = \sqrt{\frac{n_e e^2}{\epsilon_0 m_e}}
\]

Treat the crossover condition as satisfied when:

- the ionization state produces a sufficiently large electron density `n_e`
- the plasma frequency exceeds the operating frequency: `ω < ω_p`
- the plasma regime is intended to dominate neutral-collision behavior

### Skin depth and shielding effectiveness

For the field-dominated shield layer, use:

\[
\delta = \sqrt{\frac{2}{\omega \mu_0 \sigma}}
\]

\[
SE_{dB} \approx 8.686 \cdot \left(\frac{t}{\delta}\right)
\]

### Baseline simulator inputs

Use these defaults for Module 2:

- **Indium layer thickness (`t`)**: `100 µm` default benchmark
- **Target operating frequency**: `5.03 MHz`
- **Transition plot**: enabled, showing shielding effectiveness as electron density `n_e` rises

### Suggested calculator inputs

The simulator baseline should accept:

- shield thickness `t`
- operating frequency `f` or angular frequency `ω`
- conductivity `σ`
- electron density `n_e`

The simulator should calculate:

- plasma frequency `ω_p`
- skin depth `δ`
- shielding effectiveness in dB
- whether the shield is above crossover for the selected operating frequency