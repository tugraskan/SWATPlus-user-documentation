---
description: Annual phosphorus loss-rate coefficient used outside the mid-year nutrient period
---

# p\_stl

**Code reference:** `res_nut(ires)%psetlr2` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_data_module.f90#L116)).

Annual particulate phosphorus loss-rate coefficient (`1/year`; historical table default: `10.0`, range `2.0–20.0`; Fortran struct default: `0.`) applied outside the mid-year period defined by [mid\_start](mid_start.md) and [mid\_end](mid_end.md). SWAT+ divides the annual value by `365` in [`res_read_nut.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_read_nut.f90#L66) and applies it to sediment-bound phosphorus (`sedp`) in [`res_nutrient.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_nutrient.f90#L64-L94):

$$f_P = \min\!\left(1,\; \max\!\left(0,\; (C_P - C_{P,\min}) \, \frac{k_{P,2}}{365} \, \theta_P^{(T - 20)}\right)\right), \qquad M_{\text{sedP,new}} = M_{\text{sedP}} (1 - f_P)$$

where $C_P$ is particulate phosphorus concentration (ppm), $C_{P,\min}$ is [p\_min\_stl](p_min_stl.md) (ppm), $k_{P,2}$ is `p_stl` (`1/year`), $\theta_P$ is [theta\_p](theta_p.md), and $T$ is daily average air temperature (`deg C`).
