---
description: Nitrogen uptake distribution parameter
---

# n\_uptake

**Code reference:** `bsn_prm%n_updis` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L88), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_prm.f90#L24)).

Controls the vertical depth distribution of plant nitrate uptake through the root zone (default `20`, range `0–100`; values `< 1.e-6` are reset to `20.0` in [`basin_prm_default.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_prm_default.f90#L15)). Using the normalization factor computed at [`basin_prm_default.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_prm_default.f90#L56), [`pl_nup.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_nup.f90#L81) calculates potential cumulative N uptake to depth $z$:

$$U_{N,\max}(z) = U_{N,d}\,r_{NO3}\,\frac{1 - \exp(-\beta_n\,z / z_{\text{root}})}{1 - \exp(-\beta_n)}$$

where $\beta_n$ is `n_uptake`, $U_{N,d}$ is plant nitrogen demand, $r_{NO3}$ is the plant demand ratio, and $z_{\text{root}}$ is root depth. Because the top 10 mm interacts with surface runoff, $\beta_n$ influences surface nitrate availability while deeper layers can compensate for upper-layer depletion.
