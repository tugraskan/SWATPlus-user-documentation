---
description: Currently not used in SWAT+ main (6f515368)
---

# org\_min

**Code reference:** `aqu_init_dat_c(iaqu)%org_min` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/aquifer_module.f90#L77)).

SWAT+ main (6f515368) reads the org_min field from initial.aqu but does not use it afterward. The aquifer organic-mineral initialization loop in this version does not apply this pointer, and initial.aqu_cs has no org_min field.
