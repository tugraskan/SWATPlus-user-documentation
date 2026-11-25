---
description: "Secondary action value"
---

# const2

**Code reference:** `dtbl_scen(i)%act(iac)%const2` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditional_module.f90#L24)).

Second numeric action parameter where the action uses it. The implementation does not enforce a change-count limit from this field for `lu_change` or `snow_change`. Both branches increment their counters, and the land-use limit check is commented out. [`actions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L1008-L1020) · [`actions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L1054-L1067)
