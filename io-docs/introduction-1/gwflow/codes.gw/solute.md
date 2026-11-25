---
description: "Solute transport from solute.gw (1 = on)"
---

# solute

**Code reference:** `gw_solute_flag` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_module.f90#L500), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L251)).

1 turns the process on; 0 (or a missing setting) leaves it off. When on and [solute.gw](../solute.gw/README.md) exists, nitrate and phosphorus are transported in groundwater, plus the salt ions and other constituents named in `constituents.cs` ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1587-L1640)). If `solute.gw` is missing, SWAT+ sets the setting to 0 ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1907-L1909)).
