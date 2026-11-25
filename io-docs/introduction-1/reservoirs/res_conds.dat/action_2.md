---
description: "Numeric action applied when this module condition entry is satisfied"
---

# action

**Code reference:** `ctbl(ictbl)%mods(imod)%con(ii)%action` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_conditions_module.f90#L19)).

Daily reservoir outflow volume ($\text{m}^3$/day) assigned directly to `ht2%flo` in [`res_rel_conds.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_rel_conds.f90#L68) when the module condition entry is satisfied. If no entry in the module is satisfied, outflow is set to `0.`.
