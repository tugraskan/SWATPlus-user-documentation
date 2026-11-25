---
description: Beginning month of the mid-year nutrient settling period
---

# mid\_start

**Code reference:** `res_nut(ires)%ires1` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_data_module.f90#L111)).

Beginning month (`1–12`; historical table default: `5`; Fortran struct default: `0`) of the mid-year nutrient settling season. In [`res_nutrient.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_nutrient.f90#L59-L64), when the current month satisfies `mid_start` $\le m \le$ [mid\_end](mid_end.md), SWAT+ uses [mid\_n\_stl](mid_n_stl.md) and [mid\_p\_stl](mid_p_stl.md); otherwise it uses [n\_stl](n_stl.md) and [p\_stl](p_stl.md).

This seasonal split allows different settling rates for temperature or stratification regimes. To apply one rate year-round, set both periods to the same rate; setting all settling rates to `0` disables nutrient settling.
