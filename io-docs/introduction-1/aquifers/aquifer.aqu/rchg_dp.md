---
description: Fraction of aquifer recharge that seeps to a deeper aquifer
---

# rchg\_dp

**Code reference:** `aqudb(i)%seep` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aquifer_module.f90#L18)).

Fraction of the day's aquifer recharge that seeps to a deeper aquifer. In [`aqu_1d_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_1d_control.f90#L123-L127), seepage is calculated as follows:

$$
W_{\text{seep}} = \min\left(R \times f_{\text{seep}},\; S\right)
$$

where $R$ is the recharge (mm), $f_{\text{seep}}$ is _rchg\_dp_, and $S$ is storage (mm). Seepage is removed from storage and placed in the aquifer's second (deep-recharge) output hydrograph, along with proportional nitrate and pesticide.

That hydrograph can be routed to a deeper aquifer or any other object through [**aquifer.con**](../../connectivity/hru.con/). If it is not routed, the seepage leaves the watershed.
