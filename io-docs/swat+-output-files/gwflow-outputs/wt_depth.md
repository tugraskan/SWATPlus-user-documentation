---
description: "Ground-surface elevation minus period head"
---

# wt_depth

**Code reference:** daily `gw_state(i)%elev - gw_state(i)%head`; longer periods subtract the corresponding mean head from the same cell elevation ([daily](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L1231); [monthly](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L1363); [yearly](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L1620); [average annual](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L2025)).

Depth is calculated as surface elevation minus [head](head.md). Monthly and yearly values use the corresponding period mean head. Average annual uses the mean of yearly mean heads divided by configured `time%nbyr`. The expression has no lower bound at zero here; head above surface produces negative depth.

The calendar divisors also affect reported depth when the simulation [starts partway through a month or year](cell-water-balance.md#partial-reporting-periods).

**Unit:** m.

[Back to the cell water-balance schema](cell-water-balance.md).
