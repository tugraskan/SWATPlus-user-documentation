---
description: Currently not used in SWAT+ main (6f515368)
---

# name (initial.aqu)

**Code reference:** `aqu_init_dat_c(iaqu)%name`

**Declared type:** `aquifer_init_data_char` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/aqu_read_init.f90#L53), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/aquifer_module.f90#L76)).

SWAT+ main (6f515368) reads the name field from initial.aqu but does not use it afterward. Active aquifer initialization-name matching is performed with records read from initial.aqu_cs.
