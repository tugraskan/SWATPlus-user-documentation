---
description: Bulk density of benthic sediment
---

# bd

**Code reference:** `res_sed(ires)%bd` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_data_module.f90#L103)).

Bulk density of benthic sediment (`t/m3`; Fortran struct default: `0.`). During reservoir initialization ([`res_initial.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_initial.f90#L113)), SWAT+ uses `bd` to compute the water–benthic pesticide mixing velocity applied in [`res_pest.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_pest.f90#L124):

$$v_{\text{mix}} = M_w \left(1 - \frac{\rho_b}{2.65}\right)$$

where $v_{\text{mix}}$ is the diffusive mixing velocity, $M_w$ is the pesticide molecular weight, $\rho_b$ is `bd` (`t/m3`), and `2.65` is sediment particle density (`t/m3`). In [`res_pest.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_pest.f90#L63-L69), `bd` also enters the solid-to-water ratio before the benthic dissolved fraction `fd2` is overwritten with $1 / (0.8 + 0.026 \, K_d)$:

$$r_{\text{sw}} = \frac{\rho_b}{1 - \rho_b / 2.65}$$

where $r_{\text{sw}}$ is the benthic sediment-to-water mass ratio (dimensionless) and $\rho_b$ is `bd` (`t/m3`).
