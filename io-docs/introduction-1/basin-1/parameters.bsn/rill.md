---
description: Rill erosion coefficient
---

# rill

**Code reference:** `bsn_prm%rill_mult` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L126), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_prm.f90#L24)).

Rill-erosion multiplier to top-layer soil erodibility (`USLE_K`) for soils susceptible to rill erosion ($c_{\text{rill}}$, table default `0.7`, range `0.5–2`; struct and runtime fallback default `0.` when `< 1.e-6` in [`basin_prm_default.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_prm_default.f90#L47)).

Active when [gampt](../codes.bsn/gampt.md) `> 0`, [`ero_ovrsed.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ero_ovrsed.f90#L197-L198) computes overland-flow erosion rate (`kg/hr/m^2`) as:

$$E_{\text{ov}} = 11.02\,c_{\text{rill}}\,K_{\text{USLE}}\,c_{\text{mgt}}\,C\,\tau^{\beta}$$

where $K_{\text{USLE}}$ is surface soil erodibility, $c_{\text{mgt}}$ is [cov\_mgt](cov_mgt.md), $C$ is the cover factor, $\tau$ is bed shear stress (`N/m^2`), and $\beta$ is [surq\_exp](surq_exp.md).
