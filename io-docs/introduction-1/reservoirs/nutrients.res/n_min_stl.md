---
description: Minimum nitrogen concentration for settling
---

# n\_min\_stl

**Code reference:** `res_nut(ires)%conc_nmin` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_data_module.f90#L121)).

Minimum nitrogen concentration (`ppm`, i.e., `mg/L`; default: `0.10`) below which particulate organic nitrogen and soluble inorganic nitrogen settling ceases. In [`res_nutrient.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_nutrient.f90#L70-L86), SWAT+ first computes water-body concentrations:

$$C = \frac{1000 \, M}{V}$$

where $C$ is water-body concentration (ppm), $M$ is constituent mass (kg), and $V$ is reservoir volume ($\text{m}^3$). SWAT+ then drives daily loss with $(C - C_{N,\min})$, clamping negative fractions to `0`:

$$f_N = \min\!\left(1,\; \max\!\left(0,\; (C - C_{N,\min}) \, k(T)\right)\right)$$

where $f_N$ is the daily nitrogen settling fraction (dimensionless), $C$ is water-body concentration (ppm), $C_{N,\min}$ is `n_min_stl` (ppm), and $k(T)$ is the temperature-adjusted daily nitrogen loss rate.
