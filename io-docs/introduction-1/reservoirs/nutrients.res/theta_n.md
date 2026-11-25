---
description: Temperature adjustment for nitrogen loss (settling)
---

# theta\_n

**Code reference:** `res_nut(ires)%theta_n` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_data_module.f90#L119)).

Dimensionless Arrhenius temperature adjustment factor for nitrogen settling and soluble nitrogen loss (default: `1.0`). SWAT+ calls [`theta.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/theta.f90#L17) from [`res_nutrient.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_nutrient.f90#L78) for particulate organic nitrogen and [`res_nutrient.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_nutrient.f90#L84) for soluble inorganic nitrogen:

$$k(T) = k_{20} \, \theta_N^{(T - 20)}$$

where $k_{20}$ is the daily loss rate at 20 °C (`1/day`), $\theta_N$ is `theta_n`, and $T$ is daily average air temperature (`deg C`). Setting `theta_n = 1.0` disables temperature adjustment.
