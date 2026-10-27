---
description: Currently not used in initial.aqu in SWAT+ main (6f515368)
---

# pest

**Code reference:** `aqu_init_dat_c(iaqu)%pest`

**Declared type:** `aquifer_init_data_char` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/aqu_read_init.f90#L53), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/aquifer_module.f90#L78)).

SWAT+ main (6f515368) reads the pest field from initial.aqu but does not use it afterward. The active aquifer pesticide initialization pointer is read from initial.aqu_cs.
