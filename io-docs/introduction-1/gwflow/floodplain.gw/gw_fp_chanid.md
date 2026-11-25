---
description: "Channel whose floodplain covers the cell"
---

# gw_fp_chanid

**Code reference:** `gw_fp_chanid(i)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_module.f90#L309), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1192)).

Number of the SWAT+ channel whose floodplain covers the cell. The exchange runs when that channel floods and uses its depth `chd` for the stage ([`gwflow_floodplain.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_floodplain.f90#L55-L64)). The number is not checked against the number of channels.
