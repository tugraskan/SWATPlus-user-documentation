---
description: "Area of the HRU–cell intersection, m²"
---

# poly_area

**Code reference:** `poly_area` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L155), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L2165)).

Area of the intersection between the HRU and the cell, in m². It gives two fractions ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L2175-L2176)):

$$f_{\text{HRU}} = \frac{A_{\text{poly}}}{A_{\text{HRU}}}, \qquad f_{\text{cell}} = \frac{A_{\text{poly}}}{A_{\text{cell}}}$$

where:
- $f_{\text{HRU}}$ is the fraction of the HRU in the cell (dimensionless),
- $f_{\text{cell}}$ is the fraction of the cell occupied by the HRU (dimensionless),
- $A_{\text{poly}}$ is `poly_area` ($\text{m}^2$),
- $A_{\text{HRU}}$ is [hru_area](hru_area.md) ($\text{m}^2$), and
- $A_{\text{cell}}$ is the cell's [area](../cells.gw/area.md) ($\text{m}^2$).

The HRU fraction splits recharge and ET among cells; the cell fraction sizes soil transfer and wetland exchange.
