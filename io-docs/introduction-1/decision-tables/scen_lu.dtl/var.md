---
description: "Keyword naming the quantity tested"
---

# var

**Code reference:** `dtbl_scen(i)%cond(ic)%var` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditional_module.f90#L8)).

Keyword naming the quantity tested for each HRU, for example `year_cal`, `jday`, `land_use`, `hyd_soil_group`, or `slope`. All keywords are listed on the [lum.dtl var page](../lum.dtl/var.md). Do not use `days_act`, `prob_unif`, or `prob_unif_lu` here: the scenario reader does not fill the action index, application fraction, or land-use count they need. An unrecognized keyword is ignored without a warning. [`dtbl_scen_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dtbl_scen_read.f90#L63-L66) · [`time_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/time_control.f90#L218-L226)
