---
description: "First-order degradation constant for boron at 20 deg C"
---

# k\_born

**Code reference:** `res_cs_data(ires)%k_born` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_cs_module.f90#L46)).

First-order chemical reaction/degradation rate constant for boron at 20 °C (`1/day`; Fortran struct default: `0.00`). Temperature-adjusted via [`theta.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/theta.f90#L17) and applied in [`res_cs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_cs.f90#L107-L109) for reservoirs and [`wet_cs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_cs.f90#L110-L112) for wetlands (capped at available mass):

$$k_{\text{react}} = k_{20} \, \theta^{(T - 20)}, \qquad M_{\text{rctn}} = \frac{C_{\text{beg}}}{1000} \cdot k_{\text{react}} \cdot V$$

where $k_{20}$ is `k_born` (`1/day`), $\theta$ is [theta\_born](theta_born.md), $T$ is daily average air temperature (`deg C`), $C_{\text{beg}}$ is beginning-of-day concentration (`g/m3`), $V$ is water volume ($\text{m}^3$), and $M_{\text{rctn}}$ is daily reaction removal mass (kg/day).
