---
description: "Temperature adjustment factor for boron degradation"
---

# theta\_born

**Code reference:** `res_cs_data(ires)%theta_born` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_cs_module.f90#L49)).

Dimensionless Arrhenius temperature adjustment factor for boron degradation (Fortran struct default: `1.08`). SWAT+ passes it to [`theta.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/theta.f90#L17) from [`res_cs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_cs.f90#L107) and [`wet_cs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_cs.f90#L110):

$$k_{\text{react}} = k_{20} \, \theta^{(T - 20)}$$

where $k_{20}$ is [k\_born](k_born.md) (`1/day`), $\theta$ is `theta_born`, and $T$ is daily average air temperature (`deg C`).
