---
description: "Number of release modules associated with this table"
---

# num\_modules

**Code reference:** `ctbl(ictbl)%num_modules` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_conditions_module.f90#L32)).

Number of release modules associated with this condition table. SWAT+ allocates `ctbl(ictbl)%mods(num_modules)` in [`res_read_conds.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_read_conds.f90#L32-L34) and reads each module block in sequence.
