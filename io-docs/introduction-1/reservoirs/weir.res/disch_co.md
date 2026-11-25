---
description: Weir discharge linear coefficient
---

# linear\_c

**Code reference:** `res_weir(ires)%c` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_data_module.f90#L139)).

Dimensionless linear coefficient in the weir-release equation (Fortran struct default: `1.84`). SWAT+ calculates weir discharge in [`res_hydro.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_hydro.f90#L199-L208) and [`res_weir_release.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_weir_release.f90#L84-L104) as:

$$Q = 0.45 \, A \cdot c \cdot w \cdot h_{\text{above}}^{k}$$

where:

- $Q$ is the discharge rate (`m3/s` in source comments, integrated over the sub-daily/hourly step to $\text{m}^3$)
- $A$ is surface area (ha)
- $c$ is `linear_c` (dimensionless)
- $w$ is [width](weir_wd.md) (m)
- $k$ is [exp\_k](energy_co.md) (dimensionless)
- $h_{\text{above}}$ is water depth above the weir crest (m)

Water depth above the weir crest is computed as:

$$h_{\text{above}} = \max(0,\, d - h_{\text{weir}})$$

where $h_{\text{above}}$ is water depth above the weir crest (m), $d$ is water depth (m), and $h_{\text{weir}}$ is weir-crest height (m).
