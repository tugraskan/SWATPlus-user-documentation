---
description: Weir discharge exponential coefficient
---

# exp\_k

**Code reference:** `res_weir(ires)%k` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_data_module.f90#L140)).

Dimensionless exponent applied to water depth above the weir crest in the weir-release equation (Fortran struct default: `2.6`). In [`res_hydro.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_hydro.f90#L199-L208) and [`res_weir_release.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_weir_release.f90#L84-L104), SWAT+ computes:

$$Q = 0.45 \, A \cdot c \cdot w \cdot h_{\text{above}}^{k}$$

where $A$ is surface area (ha), $c$ is [linear\_c](disch_co.md), $w$ is [width](weir_wd.md) (m), $k$ is `exp_k`, $h_{\text{above}}$ is water depth above the weir crest (m), and $Q$ is the discharge rate (`m3/s` in source comments, integrated over the sub-daily/hourly step to $\text{m}^3$).
