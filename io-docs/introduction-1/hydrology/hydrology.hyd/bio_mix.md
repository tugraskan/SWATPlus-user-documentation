---
description: Biological mixing efficiency
---

# bio\_mix

**Code reference:** `hyd_db(ithyd)%biomix` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrology_data_module.f90#L18)).

Dimensionless efficiency of soil redistribution by soil organisms. In the `cswat = 0` path, annual processing calls the soil mixing routine when this value exceeds $10^{-6}$. The built-in hydrology record uses zero. [`time_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/time_control.f90#L339-L342) The `cswat = 2` daily path uses a separate efficiency set by the tillage reader. [`hru_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_control.f90#L396-L398) · [`till_parm_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/till_parm_read.f90#L47-L59)
