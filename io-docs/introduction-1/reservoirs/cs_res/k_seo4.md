---
description: "First-order degradation constant for selenate at 20 deg C"
---

# k\_seo4

**Code reference:** `res_cs_data(ires)%k_seo4` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_cs_module.f90#L44)).

First-order chemical reaction/degradation rate constant for selenate at 20 °C (`1/day`; Fortran struct default: `0.05`). Temperature-adjusted via [`theta.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/theta.f90#L17) and applied in [`res_cs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_cs.f90#L103-L109) for reservoirs and [`wet_cs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_cs.f90#L106-L112) for wetlands (capped at available mass):

$$k_{\text{react}} = k_{20} \, \theta^{(T - 20)}, \qquad M_{\text{rctn}} = \frac{C_{\text{beg}}}{1000} \cdot k_{\text{react}} \cdot V$$

where $k_{20}$ is `k_seo4` (`1/day`), $\theta$ is [theta\_seo4](theta_seo4.md), $T$ is daily average air temperature (`deg C`), $C_{\text{beg}}$ is beginning-of-day concentration (`g/m3`), $V$ is water volume ($\text{m}^3$), and $M_{\text{rctn}}$ is daily reaction removal mass (kg/day, converted to `seo3` production).
