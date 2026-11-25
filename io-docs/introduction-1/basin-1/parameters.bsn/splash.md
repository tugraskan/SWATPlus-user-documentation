---
description: Splash erosion coefficient
---

# splash

**Code reference:** `bsn_prm%eros_spl` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L125), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_prm.f90#L24)).

Raindrop splash-erosion water-depth attenuation coefficient ($\alpha_{\text{spl}}$, table default `1`, range `0.9–3.1`; struct and runtime fallback default `0.` when `< 1.e-6` in [`basin_prm_default.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_prm_default.f90#L46)).

Active when [gampt](../codes.bsn/gampt.md) `> 0`, [`ero_ovrsed.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ero_ovrsed.f90#L164-L165) computes soil detachment by raindrop impact (`tons`) as:

$$E_{\text{spl}} = K_{\text{erod}}\,\text{KE}_{\text{tot}}\,\exp\!\left(-\alpha_{\text{spl}}\,\frac{h}{1000}\right)\,A_{\text{km}}$$

where $K_{\text{erod}}$ is soil detachability, $\text{KE}_{\text{tot}}$ is total rainfall kinetic energy (`J/m^2`), $h$ is overland flow depth (`mm`), and $A_{\text{km}}$ is HRU area (`km^2`).
