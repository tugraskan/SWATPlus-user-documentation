---
description: "Aquifer specific yield, fraction"
---

# aquifer_Sy

**Code reference:** `zones_aquSy(i)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L95), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L398)).

Specific yield of the aquifer, as a fraction. Each cell takes the value of its `Sy_zone` ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L462)). It converts a volume change into a head change ([`gwflow_lateral.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_lateral.f90#L150-L153)):

$$\Delta h = \frac{\Delta V}{S_{y} \, A}$$

where $\Delta V$ is the net volume added (m³) and $A$ the cell area (m²). A zero value makes this division fail. The calibration parameter `aquifer_Sy` changes the value cell by cell ([`cal_parm_select.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_parm_select.f90#L1066-L1069)).
