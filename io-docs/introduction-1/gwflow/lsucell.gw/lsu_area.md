---
description: "Total LSU area, m²"
---

# lsu_area

**Code reference:** `lsu_area` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L157), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L2108)).

Total area of the LSU, in m². The intersection area is divided by it to get the fraction of the LSU's recharge and ET given to the cell ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L2115)):

$$f = \frac{A_{\text{poly}}}{A_{\text{LSU}}}$$

where $f$ is the fraction of the LSU in the cell (dimensionless), $A_{\text{poly}}$ is [poly_area](poly_area.md) ($\text{m}^2$), and $A_{\text{LSU}}$ is `lsu_area` ($\text{m}^2$).

For each LSU the fractions should add up to 1; SWAT+ does not check this.
