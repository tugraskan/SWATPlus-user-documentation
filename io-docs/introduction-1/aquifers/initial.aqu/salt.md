---
description: Pointer to the salt initialization file (read but not used in main 6f515368)
---

# salt

**Code reference:** `aqu_init_dat_c(iaqu)%salt` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aquifer_module.f90#L81)).

Intended pointer to a salt initialization record. [`aqu_read_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_read_init.f90#L53) reads it, but nothing uses it afterward. Aquifer salt initialization uses the `salt` column of [initial.aqu\_cs](../../initialization/initial.aqu_cs/) instead.

*(Note: In SWAT+ main (6f515368) and dev (aa4179fe), this column is parsed into memory but is not used in simulation calculations).*
