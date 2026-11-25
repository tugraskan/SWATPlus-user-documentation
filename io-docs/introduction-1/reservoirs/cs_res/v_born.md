---
description: "Settling velocity for boron"
---

# v\_born

**Code reference:** `res_cs_data(ires)%v_born` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_cs_module.f90#L43)).

Settling velocity for boron (`m/day`; Fortran struct default: `0.001`). Daily settling mass is computed in [`res_cs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_cs.f90#L91-L93) for reservoirs and [`wet_cs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_cs.f90#L94-L96) for wetlands (capped at available mass):

$$M_{\text{settle}} = \frac{C_{\text{beg}}}{1000} \cdot v_{\text{settle}} \cdot (10000 \, A)$$

where $M_{\text{settle}}$ is daily settling mass (kg/day), $C_{\text{beg}}$ is beginning-of-day boron concentration (`g/m3`), $v_{\text{settle}}$ is `v_born` (`m/day`), and $A$ is water-body surface area (ha).
