---
description: "Name of the source variable compared in this module condition entry"
---

# var

**Code reference:** `ctbl(ictbl)%mods(imod)%con(ii)%scon(icc)%var` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_conditions_module.f90#L12)).

Name of the source variable compared in a module condition entry. Accepted values in [`res_rel_conds.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_rel_conds.f90#L52-L58) are `inflo` (daily inflow volume, $\text{m}^3$) and `stor` (current reservoir storage, $\text{m}^3$).
