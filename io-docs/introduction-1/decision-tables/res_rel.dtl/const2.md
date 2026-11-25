---
description: "Secondary action value"
---

# const2

**Code reference:** `dtbl_res(i)%act(iac)%const2` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditional_module.f90#L24)).

Second numeric parameter of the [release option](option.md): m³/s added to inflow for `inflo_rate`, multiplier on the named storage for `days`, percent of principal storage per day for `dyrt` and `dyrt1`, release coefficient (1/d) for `natlake`, beta for `irr-h06`, and phase for `hydrop`. For `days` with `pvol` or `evol`, enter 1 to draw down to that storage. [`res_hydro.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_hydro.f90#L112-L114) · [`res_hydro.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_hydro.f90#L124-L135)

The calibration parameter `withdraw_rate` changes this value for the action row given by its layer number. [`cal_parm_select.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_parm_select.f90#L922-L926)
