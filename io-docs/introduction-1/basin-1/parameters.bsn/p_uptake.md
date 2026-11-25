---
description: Phosphorus uptake distribution parameter
---

# p\_uptake

**Code reference:** `bsn_prm%p_updis` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L89), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_prm.f90#L24)).

Controls the vertical depth distribution of plant solution-phosphorus uptake in the same manner as [n\_uptake](n_uptake.md) (default `20`, range `0–100`; values `< 1.e-6` are reset to `20.0` in [`basin_prm_default.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_prm_default.f90#L16)). Using the normalization factor at [`basin_prm_default.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_prm_default.f90#L57), [`pl_pup.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_pup.f90#L70) calculates potential cumulative P uptake to depth $z$:

$$U_{P,\max}(z) = U_{P,d}\,r_{P}\,\frac{1 - \exp(-\beta_p\,z / z_{\text{root}})}{1 - \exp(-\beta_p)}$$

where $\beta_p$ is `p_uptake`, $U_{P,d}$ is plant phosphorus demand, $r_P$ is the solution-P demand ratio, and $z_{\text{root}}$ is root depth.
