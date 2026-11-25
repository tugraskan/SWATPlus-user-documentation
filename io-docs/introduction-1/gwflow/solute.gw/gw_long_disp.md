---
description: "Longitudinal dispersivity, m"
---

# gw_long_disp

**Code reference:** `gw_long_disp` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_module.f90#L503), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1648)).

Longitudinal dispersivity of the aquifer, in m, for all solutes ([`gwflow_solute.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_solute.f90#L80-L92)). The dispersive mass flux between a cell and each neighbor is

$$J = \alpha \, \frac{C_{n} - C_{i}}{L} \, \bar b$$

where:
- $J$ is the dispersive mass flux into the cell ($\text{g}/\text{day}$),
- $\alpha$ is `gw_long_disp` (m),
- $C_{n}$ and $C_{i}$ are the solute concentrations in neighbor cell $n$ and cell $i$ ($\text{g}/\text{m}^3$),
- $L$ is the connection width between the two cells ($\sqrt{\min(A_{i}, A_{n})}$, m), and
- $\bar b$ is the mean saturated thickness at the interface (m).
