---
description: "Temperature adjustment factor for selenate degradation"
---

# theta\_seo4

**Code reference:** `res_cs_data(ires)%theta_seo4` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_cs_module.f90#L47)).

Dimensionless Arrhenius temperature adjustment factor for selenate degradation (Fortran struct default: `1.08`). SWAT+ passes it to [`theta.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/theta.f90#L17) from [`res_cs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_cs.f90#L103) and [`wet_cs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_cs.f90#L106):

$$k_{\text{react}} = k_{20} \, \theta^{(T - 20)}$$

where $k_{20}$ is [k\_seo4](k_seo4.md) (`1/day`), $\theta$ is `theta_seo4`, and $T$ is daily average air temperature (`deg C`).
