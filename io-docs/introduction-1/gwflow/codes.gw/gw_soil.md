---
description: "Groundwater to soil transfer (1 = on)"
---

# gw_soil

**Code reference:** `gw_soil_flag` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_module.f90#L236), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L243)).

1 turns the process on; 0 (or a missing setting) leaves it off. When on, groundwater that rises into an HRU's soil profile is moved into the soil layers ([`gwflow_soil.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_soil.f90#L56-L64)). The volume is the saturated part of the profile, $(z_{s} - (z - h)) \, A \, S_{y}$, where $z_{s}$ is the soil-profile thickness, $z$ the cell's ground elevation, $h$ the head, $A$ the HRU–cell intersection area and $S_{y}$ the specific yield.

SWAT+ sets it to 0 when LSU links are used ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L340), [`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L352)).
