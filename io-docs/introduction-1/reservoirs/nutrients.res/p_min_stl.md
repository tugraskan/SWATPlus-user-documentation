---
description: Minimum phosphorus concentration for settling
---

# p\_min\_stl

**Code reference:** `res_nut(ires)%conc_pmin` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_data_module.f90#L122)).

Minimum phosphorus concentration (`ppm`, i.e., `mg/L`; default: `0.01`) below which particulate phosphorus and soluble phosphorus settling ceases. In [`res_nutrient.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_nutrient.f90#L71-L89), SWAT+ first computes water-body concentrations:

$$C = \frac{1000 \, M}{V}$$

where $C$ is water-body concentration (ppm), $M$ is constituent mass (kg), and $V$ is reservoir volume ($\text{m}^3$). SWAT+ then drives daily loss with $(C - C_{P,\min})$, clamping negative fractions to `0`:

$$f_P = \min\!\left(1,\; \max\!\left(0,\; (C - C_{P,\min}) \, k(T)\right)\right)$$

where $f_P$ is the daily phosphorus settling fraction (dimensionless), $C$ is water-body concentration (ppm), $C_{P,\min}$ is `p_min_stl` (ppm), and $k(T)$ is the temperature-adjusted daily phosphorus loss rate.
