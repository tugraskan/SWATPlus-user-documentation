---
description: Currently not used in initial.res in SWAT+ main (6f515368)
---

# salt

**Code reference:** `res_init_dat_c(ires)%salt` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/reservoir_data_module.f90#L48)).

SWAT+ main (6f515368) reads the salt field as part of each initial.res record but does not use its value afterward. Reservoir salt initialization instead uses the salt pointer read from reservoir.res_cs.
