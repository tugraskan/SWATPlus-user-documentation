---
description: Volume depth coefficient for HRU impoundment
---

# vol\_dp\_a

**Code reference:** `wet_hyddb(ires)%bcoef` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_data_module.f90#L91)).

The quadratic linear-term coefficient (default `1.0`) used alongside [`vol_dp_b`](vol_dp_b.md) to calculate water depth $h$ from the ratio of current water volume to principal volume ($V / V_{\text{pvol}}$) in [`wetland_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wetland_control.f90#L85-L90) and [`wet_initial.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_initial.f90#L207-L212):

$$x_1 = b^2 + 4 \cdot c \cdot \left(1 - \frac{V}{V_{\text{pvol}}}\right), \qquad h = \frac{-b - \sqrt{x_1}}{2c} + b$$

where $b$ is `vol_dp_a` and $c$ is `vol_dp_b`.

The resulting depth $h$ is subsequently multiplied by [`vol_area_co`](vol_area_co.md) to update the daily wetland surface area. If `vol_dp_a` is smaller than `vol_dp_b`, the wetland surface area shrinks more strongly as water volume declines.
