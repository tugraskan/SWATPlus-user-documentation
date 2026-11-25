---
description: "Primary action value"
---

# const

**Code reference:** `dtbl_res(i)%act(iac)%const` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditional_module.f90#L23)).

First numeric parameter of the [release option](option.md): discharge in m³/s for `rate`, percent of principal storage per day for `rate_pct`, minimum discharge in m³/s for `inflo_rate`, fraction of inflow for `inflo_frac`, drawdown days for `days`, `dyrt`, and `dyrt1`, a condition row number for `inflo_targ`, and a scheme coefficient for `natlake`, `nonirr-h06`, `irr-h06`, and `hydrop`. [`res_hydro.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_hydro.f90#L103-L118) · [`res_hydro.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_hydro.f90#L182-L184)

The calibration parameter `drawdown_days` changes this value for the action row given by its layer number, whatever the row's option is. [`cal_parm_select.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_parm_select.f90#L917-L921)
