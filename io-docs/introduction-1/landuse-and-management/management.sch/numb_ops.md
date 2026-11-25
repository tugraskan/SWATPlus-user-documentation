---
description: Number of scheduled management operations
---

# numb\_ops

**Code reference:** `sched(isched)%num_ops` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_operations_module.f90#L178), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_read_mgtops.f90#L61)).

Integer count (default `0`) of scheduled operation rows in the management schedule. It allocates `sched(isched)%mgt_ops` and controls the read loop in [`mgt_read_mgtops.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_read_mgtops.f90#L90-L91) and [`read_mgtops.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/read_mgtops.f90#L26). When `num_ops < 1`, scheduled operations are skipped in [`mgt_operatn.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_operatn.f90#L44).
