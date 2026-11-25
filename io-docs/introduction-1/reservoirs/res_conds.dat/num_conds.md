---
description: "Number of condition blocks defined for this table"
---

# num\_conds

**Code reference:** `ctbl(ictbl)%num_conds` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_conditions_module.f90#L31)).

Number of top-level condition blocks defined for this condition table. SWAT+ allocates `ctbl(ictbl)%conds(num_conds)` in [`res_read_conds.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_read_conds.f90#L32-L33) and evaluates them sequentially in [`res_rel_conds.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_rel_conds.f90#L23).
