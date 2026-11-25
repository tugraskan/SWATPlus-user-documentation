---
description: Temperature adjustment for phosphorus loss (settling)
---

# theta\_p

**Code reference:** `res_nut(ires)%theta_p` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_data_module.f90#L120)).

Dimensionless Arrhenius temperature adjustment factor for phosphorus settling and soluble phosphorus loss (default: `1.0`). SWAT+ calls [`theta.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/theta.f90#L17) from [`res_nutrient.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_nutrient.f90#L81) for particulate phosphorus and [`res_nutrient.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_nutrient.f90#L87) for soluble phosphorus:

$$k(T) = k_{20} \, \theta_P^{(T - 20)}$$

where $k_{20}$ is the daily loss rate at 20 °C (`1/day`), $\theta_P$ is `theta_p`, and $T$ is daily average air temperature (`deg C`). Setting `theta_p = 1.0` disables temperature adjustment.
