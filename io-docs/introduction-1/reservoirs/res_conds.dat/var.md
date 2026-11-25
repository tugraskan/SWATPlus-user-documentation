---
description: "Name of the source variable compared in this condition entry"
---

# var

**Code reference:** `ctbl(ictbl)%conds(ii)%scon(icc)%var` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_conditions_module.f90#L12)).

Name of the source variable compared in a top-level condition entry. Accepted values in [`res_rel_conds.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_rel_conds.f90#L26-L35) are:
- `stor`: current reservoir storage ($\text{m}^3$)
- `inflo`: daily inflow volume ($\text{m}^3$)
- `pdsi`: Palmer Drought Severity Index (passed as `0.` from [`res_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_control.f90#L164))
- `day`: Julian day of year (compared as an integer)
