---
description: "Reservoir stage; not used"
---

# res_stage

**Code reference:** `res_stage` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L112), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1146)).

Reservoir stage for the connection, in m. SWAT+ reads it but does not store or use it; the reservoir head is the ground elevation of `res_cell` ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1146-L1153)). *(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations).* This is listed in `MODEL_ISSUES.md`.
