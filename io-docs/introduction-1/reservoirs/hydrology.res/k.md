---
description: Hydraulic conductivity of the reservoir bottom
---

# k

**Code reference:** `res_hyddb(ires)%k` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_data_module.f90#L74)).

Saturated hydraulic conductivity of the reservoir bottom (`mm/hr`; historical table default: `0.0`, range `0.0–1.0`; Fortran struct default: `0.01`). If seepage occurs in the reservoir, `k` must be set greater than `0`.

When the basin groundwater-flow option (`bsn_cc%gwflow == 0`) is off, SWAT+ computes daily seepage in [`res_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_control.f90#L171-L175):

$$V_{\text{seep}} = 240 \cdot K_{\text{sat}} \cdot A$$

where $V_{\text{seep}}$ is daily seepage volume ($\text{m}^3$), $K_{\text{sat}}$ is `k` (mm/hr), $A$ is reservoir surface area (ha), and $240 = 24 \times 10$ converts mm/hr over ha to $\text{m}^3\text{/day}$ (capped at remaining reservoir storage in [`res_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_control.f90#L195-L199)). When groundwater-flow mode is active (`gwflow == 1`), reservoir seepage is calculated by `gwflow_reservoir` instead.
