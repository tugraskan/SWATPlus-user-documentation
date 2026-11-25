---
description: Intended pointer to an organic-mineral water initialization record (read but not used in main 6f515368)
---

# org\_min

**Code reference:** `aqu_init_dat_c(iaqu)%org_min` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aquifer_module.f90#L77)).

Intended pointer to an organic-mineral water initialization record in [om\_water.ini](../../initialization/om_water.ini/). [`aqu_read_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_read_init.f90#L53) reads it, but nothing uses it afterward. Initial aquifer nutrients come from [no3\_n](../aquifer.aqu/no3_n.md) and [sol\_p](../aquifer.aqu/sol_p.md) in **aquifer.aqu**. The separate `initial.aqu_cs` record type has no `org_min` field.

*(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations).*
