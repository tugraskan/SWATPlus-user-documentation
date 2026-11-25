---
description: "Number of HRUs in the irrigation group"
---

# hrus

**Code reference:** `hruirr_db(irr)%hrus` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L59), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_hru_irr_read.f90#L40)).

Number of HRU member rows following this group header (default: `0`). Allocates `hru_num` and `dtbl_lum` ([`water_hru_irr_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_hru_irr_read.f90#L41-L43)) and is copied into `pou(ipou)%irr%hru_num` for `"irr"` POUs in [`water_allocation_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_read.f90#L123-L124).
