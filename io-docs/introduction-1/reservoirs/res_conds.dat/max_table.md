---
description: "Number of release condition tables to read for reservoirs"
---

# max\_table

**Code reference:** `max_table` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_read_conds.f90#L9)).

Number of release condition tables to read from `res_conds.dat`. In [`res_read_conds.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_read_conds.f90#L24-L28), SWAT+ allocates `ctbl(max_table)` and sets `db_mx%ctbl_res = max_table`; if `max_table < 1`, reading stops immediately.
