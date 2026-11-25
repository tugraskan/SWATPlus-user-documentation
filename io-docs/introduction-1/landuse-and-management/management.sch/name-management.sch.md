---
description: Name of the management schedule
---

# name (management.sch)

**Code reference:** `sched(isched)%name` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_operations_module.f90#L177), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_read_mgtops.f90#L61)).

Character string (`len=40`, default `""`) naming the management schedule. This primary key is referenced by [mgt](../landuse.lum/mgt.md) in [**landuse.lum**](../landuse.lum/README.md) ([`landuse_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/landuse_read.f90#L72)). All names in `management.sch` must be unique.
