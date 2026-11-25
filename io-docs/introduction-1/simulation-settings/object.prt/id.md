---
description: ID of the object print record
---

# id

**Code reference:** `ii` / `k` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/object_read_output.f90#L15-L16)).

Integer record index for each row in `object.prt`. During reading in [`object_read_output.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/object_read_output.f90#L34-L53), SWAT+ first scans the file to find `imax` (maximum `id`) and `mobj_out` (row count), allocates `ob_out(0:imax)`, and stores each row into `ob_out(ii)`.

Because the subsequent initialization loop processes `ob_out(i)` for `i = 1, mobj_out` ([`object_read_output.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/object_read_output.f90#L48-L118)), `id` values must be sequential integers starting at `1` (`1, 2, ..., mobj_out`).
