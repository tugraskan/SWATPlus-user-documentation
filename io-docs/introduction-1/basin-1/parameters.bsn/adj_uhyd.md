---
description: Adjustment factor for subdaily unit hydrograph basetime
---

# adj\_uhyd

**Code reference:** `bsn_prm%tb_adj` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L114), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_prm.f90#L24)).

Additive adjustment (`hours`, default `0`, range `0–1`; values `< 1.e-6` are reset to `0.` in [`basin_prm_default.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_prm_default.f90#L36)) to the sub-daily unit hydrograph basetime in [`unit_hyd.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/unit_hyd.f90#L73-L75):

$$t_b = \min\!\big(48,\; 0.5 + 0.6\,t_c + t_{b,\text{adj}}\big), \qquad t_p = 0.375\,t_b$$

where $t_b$ is unit hydrograph basetime (`hours`), $t_c$ is HRU time of concentration (`hours`), $t_{b,\text{adj}}$ is `adj_uhyd`, and $t_p$ is time to peak (`hours`).
