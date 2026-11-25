---
description: Soil water factor for CN3
---

# cn3\_swf

**Code reference:** `hlt_db(i)%cn3_swf` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_module.f90#L13)).

Sets the soil water content that corresponds to curve number condition III, as a position between field capacity (0) and saturation (1) ([`hru_lte_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_read.f90#L265-L268)):

$$SW_3 = AWC + f \, (POR - AWC)$$

where $SW_3$ is the soil water content corresponding to curve number condition III (`mm`), $f$ is `cn3_swf` (dimensionless), and $AWC$ and $POR$ are the profile water contents (`mm`) obtained from [soil\_text](soil_text.md) and [soil\_dp](soil_dp.md).
