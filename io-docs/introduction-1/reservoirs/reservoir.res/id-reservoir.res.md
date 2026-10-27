---
description: ID of the reservoir
---

# id (reservoir.res)

**Code reference:** `k`

**Declared type:** `integer` (variable in `res_read`) ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/res_read.f90#L74), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/res_read.f90#L30)).

The ID of the reservoir is a primary key referenced by the foreign key [res](../../connectivity/hru.con/hru.md) in [**reservoir.con**](../../connectivity/hru.con/). All IDs in the **reservoir.res** file must be unique.
