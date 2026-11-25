---
description: "Total HRU area, m²"
---

# hru_area

**Code reference:** `hru_area` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L148), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L2165)).

Total area of the HRU, in m². SWAT+ divides each intersection area by it to get the fraction of the HRU in each cell ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L2175)):

$$f_{\text{HRU}} = \frac{A_{\text{poly}}}{A_{\text{HRU}}}$$

where $f_{\text{HRU}}$ is the fraction of the HRU in the cell (dimensionless), $A_{\text{poly}}$ is [poly_area](poly_area.md) ($\text{m}^2$), and $A_{\text{HRU}}$ is `hru_area` ($\text{m}^2$).

These fractions split the HRU's recharge and ET among its cells, so for each HRU they should add up to 1. SWAT+ does not check this. The recharge volume itself comes from the HRU area in the HRU data, not from this value.
