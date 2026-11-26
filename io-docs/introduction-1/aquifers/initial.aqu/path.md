---
description: Pointer to the pathogen initialization file (read but not used in main 6f515368)
---

# path

**Code reference:** `aqu_init_dat_c(iaqu)%path` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aquifer_module.f90#L79)).

Intended pointer to a pathogen initialization record in [path\_water.ini](../../initialization/path_water.ini/). [`aqu_read_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_read_init.f90#L53) reads it, but nothing uses it afterward. Aquifer pathogen initialization uses the `path` column of [initial.aqu\_cs](../../initialization/initial.aqu_cs/) instead.

*(Note: In SWAT+ main (6f515368) and dev (aa4179fe), this column is parsed into memory but is not used in simulation calculations).*
