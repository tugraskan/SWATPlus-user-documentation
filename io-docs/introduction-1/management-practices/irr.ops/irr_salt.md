---
description: Total salt concentration in irrigation water (copied to irrigation state but not used in calculations in main 6f515368)
---

# salt\_ppm

**Code reference:** `irrop_db(irr_op)%salt` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_operations_module.f90#L11), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_read_irrops.f90#L48)).

Total salt concentration in irrigation water (`mg/kg`; default `0.0`). During paddy irrigation setup in [`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L534), SWAT+ copies `irrop_db%salt` to `irrig(j)%salt`, but no active simulation calculation reads `irrig(j)%salt` in SWAT+ main (`6f515368`).
