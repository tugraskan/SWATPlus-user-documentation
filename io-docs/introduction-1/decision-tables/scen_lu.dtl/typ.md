---
description: "Scenario action type, such as lu_change or snow_change"
---

# typ

**Code reference:** `dtbl_scen(i)%act(iac)%typ` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditional_module.f90#L17)).

The scenario reader resolves record names for `lu_change` and `snow_change`. The general action routine also contains scenario-related actions such as `hru_fr_update` and `p_factor`. Structure actions (`tile_install`, `septic_install`, `fstrip_install`, `grassww_install`, `user_def_bmp`) and `contour`, `stripcrop`, and `terrace` also work here. Do not use field operations such as `till`, `fertilize`, or `harvest`: this reader does not look up their database records, and their yearly counters are kept only for `lum.dtl` auto-operation tables. See [lum.dtl act_typ](../lum.dtl/act_typ.md) for each action. [`dtbl_scen_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dtbl_scen_read.f90#L78-L97) · [`actions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L1000-L1021) · [`actions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L1054-L1077)
