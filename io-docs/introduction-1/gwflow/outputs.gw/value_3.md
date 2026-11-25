---
description: "Cell number; not used"
---

# value

**Code reference:** `gw_cell_obs_ss` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_module.f90#L462), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L617)).

Cell number for a `detail_debug_cell` record. SWAT+ stores it, but no routine uses it ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L616-L617)). *(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations).*
