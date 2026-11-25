---
description: Number of automatic operations (decision tables)
---

# numb\_auto

**Code reference:** `sched(isched)%num_autos` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_operations_module.f90#L179), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_read_mgtops.f90#L61)).

Integer count (default `0`) of decision-table lines listed immediately beneath the schedule header. It governs allocation and reading of [auto\_name](auto_name.md) entries in [`mgt_read_mgtops.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_read_mgtops.f90#L64-L88) and controls the daily decision-table evaluation loop in [`hru_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_control.f90#L184-L190).
