---
description: "Head for each simulation year, m"
---

# gw_tvh_vals(i,j)

**Code reference:** `gw_tvh_vals(i,j)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_module.f90#L439), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1479)).

Head for each simulation year, in m, one value per year ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1479)). *(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations).* Boundary cells use their `init` head from [cells.gw](../cells.gw/init.md) instead.
