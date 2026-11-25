---
description: ID of the reservoir
---

# id (reservoir.res)

**Code reference:** `k` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_read.f90#L30)).

The ID of the reservoir is a primary key referenced by the foreign key [res](../../connectivity/hru.con/hru.md) in [**reservoir.con**](../../connectivity/hru.con/). In [`res_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_read.f90#L71-L74), SWAT+ reads this leading integer to index `res_dat_c(ires)`. All IDs in the **reservoir.res** file must be unique.
