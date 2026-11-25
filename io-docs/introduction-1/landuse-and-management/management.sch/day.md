---
description: Day of month operation is scheduled for
---

# day

**Code reference:** `sched(isched)%mgt_ops(iop)%day` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_operations_module.f90#L161), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/read_mgtops.f90#L29)).

Integer day of month (`1–31`, default `0`; enter `0` for heat-unit-scheduled operations or `skip`). Together with [mon](mon.md), SWAT+ converts it to a Julian day `jday` in [`read_mgtops.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/read_mgtops.f90#L35-L37) and triggers date-scheduled operations when `mgt%mon == time%mo` and `mgt%day == time%day_mo` in [`mgt_operatn.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_operatn.f90#L49-L62).
