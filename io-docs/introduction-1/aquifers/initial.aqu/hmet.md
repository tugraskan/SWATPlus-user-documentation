---
description: Pointer to the heavy metal initialization file (read but not used in main 6f515368)
---

# hmet

**Code reference:** `aqu_init_dat_c(iaqu)%hmet` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aquifer_module.f90#L80)).

Intended pointer to a heavy metal initialization record. [`aqu_read_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_read_init.f90#L53) reads it, but SWAT+ does not simulate heavy metals in aquifers.

*(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations).*
