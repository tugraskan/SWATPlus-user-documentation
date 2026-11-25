---
description: "Cell area, m²"
---

# area

**Code reference:** `gw_state(i)%area` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_module.f90#L55), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L458)).

Plan area of the cell, in m². It converts volume to head change and sets the connection width between two neighbors ([`gwflow_lateral.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_lateral.f90#L64-L68)):

$$\Delta h = \frac{\Delta V}{S_{y} \, A}, \qquad L = \sqrt{\min(A_{i}, A_{n})}$$

where:
- $\Delta h$ is the head change (m),
- $\Delta V$ is the net water volume change ($\text{m}^3$),
- $S_{y}$ is specific yield (dimensionless),
- $A$ is `area` ($\text{m}^2$),
- $L$ is the connection width between neighboring cells $i$ and $n$ (m), and
- $A_{i}$ and $A_{n}$ are the areas of the two neighboring cells ($\text{m}^2$).

It also limits floodplain areas ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1196-L1199)) and converts HRU–cell intersection areas into cell fractions ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L2176)).
