---
description: Threshold depth from surface to water table for revap to occur
---

# revap\_min

**Code reference:** `aqudb(i)%revap_min` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aquifer_module.f90#L22)).

Water moves from the aquifer to the unsaturated zone only when the depth from the surface to the water table is strictly less than _revap\_min_ (m). Otherwise, [`aqu_1d_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_1d_control.f90#L130-L135) sets revap to 0. See [revap](revap.md) for the revap equation.
