---
description: ID of the aquifer
---

# id (aquifer.aqu)

**Code reference:** `i` / `k` ([reader](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_read.f90#L51-L55)).

Primary key of the aquifer record. [`aqu_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_read.f90#L51-L55) reads the ID first and uses it as the array index for the record, so IDs should be unique positive integers. The [aqu](../../connectivity/hru.con/hru.md) column in [**aquifer.con**](../../connectivity/hru.con/) references this ID.
