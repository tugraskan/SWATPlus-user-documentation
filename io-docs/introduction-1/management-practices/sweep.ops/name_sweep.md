---
description: Street sweeping operation name
---

# name (sweep.ops)

**Code reference:** `sweepop_db(isweepop)%name` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_operations_module.f90#L135), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_read_sweepops.f90#L47)).

The name of the street sweeping operation is a primary key matched when `swep` operations are scheduled in [**management.sch**](../../landuse-and-management/management.sch/README.md) ([`read_mgtops.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/read_mgtops.f90#L176-L177), [`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L480)). Street sweeping is not supported as a `lum.dtl` action in SWAT+ main (`6f515368`). All names in **sweep.ops** must be unique.

| Name      | Description              |
| --------- | ------------------------ |
| high\_eff | High-efficiency sweeping |
