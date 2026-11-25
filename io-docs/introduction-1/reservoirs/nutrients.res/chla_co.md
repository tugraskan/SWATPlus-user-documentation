---
description: Annual loss-rate coefficient for soluble inorganic nitrogen
---

# chla\_co

**Code reference:** `res_nut(ires)%nsolr` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_data_module.f90#L117)).

Despite the legacy input label, this field is the annual loss-rate coefficient for soluble inorganic nitrogen (`NO3`, `NH3`, and `NO2`; `1/year`; historical table default: `1.0`, range `0.0–1.0`; Fortran struct default: `1.`), not a chlorophyll-a production coefficient. SWAT+ divides the input by `365` in [`res_read_nut.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_read_nut.f90#L69) and applies it in [`res_nutrient.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_nutrient.f90#L84-L98):

$$f_{\text{solN}} = \min\!\left(1,\; \max\!\left(0,\; (C_{\text{solN}} - C_{N,\min}) \, \frac{k_{\text{solN}}}{365} \, \theta_N^{(T - 20)}\right)\right), \qquad M_{\text{new}} = M \,(1 - f_{\text{solN}} \, f_{\text{sol}})$$

where:

- $f_{\text{solN}}$ is the daily soluble nitrogen loss fraction (dimensionless)
- $C_{\text{solN}}$ is total soluble inorganic nitrogen concentration (ppm)
- $C_{N,\min}$ is [n\_min\_stl](n_min_stl.md) (ppm)
- $k_{\text{solN}}$ is `chla_co` (`1/year`)
- $\theta_N$ is [theta\_n](theta_n.md) (dimensionless)
- $T$ is daily average air temperature (`deg C`)
- $M$ and $M_{\text{new}}$ are the pre- and post-settling masses of each soluble nitrogen species (`no3`, `nh3`, `no2`, kg)
- $f_{\text{sol}}$ is the soluble settling fraction (`0.2`, initialized in [`res_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_read.f90#L145) and [`wet_initial.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_initial.f90#L102))
