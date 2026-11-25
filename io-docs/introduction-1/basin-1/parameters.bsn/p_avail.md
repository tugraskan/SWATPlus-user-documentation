---
description: Phosphorus availability index
---

# p\_avail

**Code reference:** `bsn_prm%psp` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L97), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_prm.f90#L24)).

Phosphorus availability index ($\text{psp}$, default `0.4`, range `0.01–0.7`; values `< 1.e-6` are reset to `0.40` in [`basin_prm_default.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_prm_default.f90#L22) and copied per HRU in [`hrudb_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hrudb_init.f90#L32)). It specifies the fraction of added fertilizer P remaining in solution after rapid equilibration between labile (solution) and active mineral phosphorus pools:

$$\text{psp} = \frac{P_{\text{sol},f} - P_{\text{sol},i}}{\text{fert}_{\text{minP}}}$$

where $P_{\text{sol},f}$ and $P_{\text{sol},i}$ are solution P after and before incubation and $\text{fert}_{\text{minP}}$ is applied soluble P fertilizer.

When the original soil P model ([soil\_p](../codes.bsn/soil_p.md) = `0`) is active, SWAT+ uses `p_avail` to initialize active mineral P in [`soil_nutcarb_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_nutcarb_init.f90#L92) and to govern daily labile–active pool equilibration in [`nut_pminrl.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/nut_pminrl.f90#L34-L42):

$$r = \frac{\text{psp}}{1 - \text{psp}}, \qquad R_{\text{mp}} = P_{\text{lab}} - r\,P_{\text{act}}$$

where positive $R_{\text{mp}}$ is scaled by `0.1` and negative $R_{\text{mp}}$ by `0.6` before updating the labile ($P_{\text{lab}}$) and active mineral ($P_{\text{act}}$) pools.
