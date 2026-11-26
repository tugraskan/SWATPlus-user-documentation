---
description: Name of the legacy aquifer initialization record (read but not used in main 6f515368)
---

# name (initial.aqu)

**Code reference:** `aqu_init_dat_c(iaqu)%name` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aquifer_module.f90#L76)).

Name of the legacy aquifer initialization record. [`aqu_read_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_read_init.f90#L53) reads it, but nothing matches against it. The [init](../aquifer.aqu/aqu_ini.md) pointer in **aquifer.aqu** is matched with names in [initial.aqu\_cs](../../initialization/initial.aqu_cs/) instead.

*(Note: In SWAT+ main (6f515368) and dev (aa4179fe), this column is parsed into memory but is not used in simulation calculations).*
