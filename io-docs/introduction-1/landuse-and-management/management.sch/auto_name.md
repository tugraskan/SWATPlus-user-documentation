---
description: Name of the decision table in lum.dtl
---

# auto\_name

**Code reference:** `sched(isched)%auto_name(iauto)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_operations_module.f90#L182), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_read_mgtops.f90#L69)).

Character string (`len=40`) acting as a foreign key referencing [name](../../decision-tables/lum.dtl/name.md) in [**lum.dtl**](../../decision-tables/lum.dtl/README.md). Each entry is crosswalked to `dtbl_lum` in [`proc_cond.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/proc_cond.f90#L21-L26) and evaluated daily for HRUs using this schedule in [`hru_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_control.f90#L185-L190).
