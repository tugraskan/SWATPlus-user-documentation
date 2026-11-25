---
description: "Contributing area"
---

# area_ha

**Code reference:** `ob(icmd)%area_ha` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L343)).

Channel object area stored in `ob(icmd)%area_ha` from the connectivity record. The duration-curve routine uses no area conversion or upstream-area sum in the active write. [Connectivity read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hyd_read_connect.f90#L220-L225), [report write](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/flow_dur_curve.f90#L145-L146).

**Unit:** ha.

This field belongs to a fixed or event-style report rather than the standard daily/monthly/yearly/average-annual series.

[Back to the output table](README.md).
