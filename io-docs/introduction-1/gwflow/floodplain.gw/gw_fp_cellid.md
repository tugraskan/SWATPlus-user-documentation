---
description: "Cell number"
---

# gw_fp_cellid

**Code reference:** `gw_fp_cellid(i)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_module.f90#L308), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1192)).

Number of a cell under the floodplain ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1192-L1195)). Only active cells exchange water. If the cell also has a channel connection in [chancell.gw](../chancell.gw/README.md), the channel's own exchange area is subtracted from the floodplain area ([`gwflow_floodplain.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_floodplain.f90#L66-L74)). With `grid_type` = `structured`, SWAT+ maps cell numbers through an identity list, so structured and unstructured grids both use cell numbers 1 to `ncell` ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L313-L319)).
