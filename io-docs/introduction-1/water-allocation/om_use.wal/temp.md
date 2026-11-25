---
description: "Water temperature"
---

# temp

**Code reference:** `wuse_om_efflu(iom_use)%temp` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L49), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/om_use_read.f90#L44)).

Water temperature (`deg C`; Fortran struct default: `0.`). [`hydrograph_module.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L1236-L1258) passes `temp` through unchanged; note that the water-use output header ([`water_allocation_module.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L306)) labels this column `null`.
