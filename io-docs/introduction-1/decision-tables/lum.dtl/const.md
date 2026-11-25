---
description: "Main numeric value of the action"
---

# const

**Code reference:** `dtbl_lum(i)%act(iac)%const` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditional_module.f90#L23)).

Main numeric value of the action; the unit follows the [action type](act_typ.md). Examples: mm for `irrigate` and `irr_demand`, kg/ha for `fertilize`, `manure`, and `pest_apply`, t/ha for `manure_demand`, the new P factor for `p_factor`, mm for `weir_height`, and the change value for `cn_update`. With the action name `ponding`, irrigation reads it as the target ponded depth in mm. [`actions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L131-L145) · [`actions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L373-L373) · [`actions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L1291-L1291)
