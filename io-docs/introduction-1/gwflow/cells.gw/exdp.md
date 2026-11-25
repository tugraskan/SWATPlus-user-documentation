---
description: "Groundwater ET extinction depth, m"
---

# exdp

**Code reference:** `gw_state(i)%exdp` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_module.f90#L60), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L454)).

Depth below the ground surface, in m, at which groundwater ET stops. The ET demand the soil could not meet is taken from the cell, scaled linearly with head ([`gwflow_gwet.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_gwet.f90#L49-L63)):

$$E = E_{\max} \, \frac{h - (z - d)}{d} \quad \text{for} \; z - d \le h \le z$$

where:
- $E$ is groundwater ET taken from the cell ($\text{m}^3$),
- $E_{\max}$ is the remaining ET volume mapped to the cell ($\text{m}^3$),
- $h$ is the head (m),
- $z$ is the ground elevation (m), and
- $d$ is `exdp` (m).

Above the surface $E$ equals $E_{\max}$; below $z - d$, $E$ is `0`. With $d$ equal to `0`, ET is taken only when the head is above the surface. The calibration parameter `aquifer_exdp` changes it cell by cell ([`cal_parm_select.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_parm_select.f90#L1078-L1081)).
