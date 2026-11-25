---
description: "Named quantity or category for the condition"
---

# lim_var

**Code reference:** `dtbl_scen(i)%cond(ic)%lim_var` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditional_module.f90#L11)).

Name used by conditions that compare against a named quantity or category. `vol` takes `pvol`, `evol`, or `e-pv`; `vol_wet` takes `pvol` or `evol`; `soil_water` takes `wp`, `fc`, or `ul`. Name-matching conditions such as `land_use`, `cal_group`, `hyd_soil_group`, `plant_com`, and `plant_name_gro` take the name to match. Enter `null` for conditions that compare only with [lim_const](lim_const.md). An unrecognized storage name gives no warning. [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L749-L779) · [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L825-L830)
