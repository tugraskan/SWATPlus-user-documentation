---
description: Volume surface area coefficient for HRU impoundment
---

# vol\_area\_co

**Code reference:** `wet_hyddb(ires)%acoef` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_data_module.f90#L90)).

A linear coefficient (default `1.0`) controlling how surface area fraction responds to changes in water depth $h$ ([`wetland_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wetland_control.f90#L92), [`wet_initial.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_initial.f90#L214)):

$$\text{fr} = 1 + a \cdot h \quad (\text{clipped to } [0.01, 1.0])$$

where $a$ is `vol_area_co`, $h$ is water depth, and $\text{fr}$ is the wetland surface area fraction (`wet_fr`).

Higher values cause the wetland surface area to expand and contract more rapidly as depth fluctuates relative to principal storage. Depth $h$ is determined each time step by the quadratic interaction of [`vol_dp_a`](vol_dp_a.md) and [`vol_dp_b`](vol_dp_b.md).
