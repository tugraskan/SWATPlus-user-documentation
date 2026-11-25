---
description: Pesticide percolation coefficient
---

# pest\_perc

**Code reference:** `bsn_prm%percop` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L99), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_prm.f90#L24)).

Controls the concentration of soluble pesticide removed from the top soil layer in surface runoff and layer-1 lateral flow relative to the concentration in percolate ($\beta_{\text{pest}}$, default `0.5`, range `0–1`; values `< 1.e-6` are reset to `0.5` in [`basin_prm_default.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_prm_default.f90#L24)).

In [`pest_lch.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pest_lch.f90#L59-L82), layer-1 surface runoff and lateral flow concentration is computed as:

$$C_{\text{surf}} = \beta_{\text{pest}}\,C_0$$

where $C_{\text{surf}}$ is the pesticide concentration in layer-1 surface runoff and lateral flow (`kg/ha/mm`), $\beta_{\text{pest}}$ is `pest_perc` (dimensionless), and $C_0$ is the solubility-capped mobile-water pesticide concentration (`kg/ha/mm`). This parameter is only important if pesticide transport is simulated.

{% hint style="info" %}
The lower *pest\_perc*, the lower the concentration of pesticide in surface runoff and layer-1 lateral flow. If *pest\_perc* = 1.0, surface runoff will have the same pesticide concentration as percolate.
{% endhint %}
