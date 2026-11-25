---
description: Depth from mid-slope surface to initial water table
---

# dep\_wt

**Code reference:** `aqudb(i)%dep_wt` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aquifer_module.f90#L10)).

Initial depth (m) from the mid-slope ground surface to the water table. [`aqu_initial.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_initial.f90#L173-L174) copies it into the daily state and uses it to calculate initial storage (see [dep\_bot](dep_bot.md)). The value should be smaller than [dep\_bot](dep_bot.md).

After initialization, the water-table depth is recomputed daily from storage in [`aqu_1d_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_1d_control.f90#L106):

$$
d_{\text{wt}} = \max\left(0,\; d_{\text{bot}} - \frac{S}{1000 \times S_{y}}\right)
$$

where $S$ is aquifer storage (mm). The current depth is compared with [flo\_min](flo_min.md) and [revap\_min](revap_min.md) to decide whether baseflow and revap occur.
