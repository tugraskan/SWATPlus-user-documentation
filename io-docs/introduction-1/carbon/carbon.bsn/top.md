---
description: "Optimum soil temperature (°C) of the decomposition temperature function"
---

# top

**Code reference:** `org_con%top` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_module.f90#L115), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_bsn_read.f90#L77), [calibration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_parm_select.f90#L505-L506)).

Temperature $T_{op}$ (°C) at which the temperature factor below reaches 1:

$$
f_T = \frac{(T - T_n)^q \, (T_x - T)}{(T_{op} - T_n)^q \, (T_x - T_{op})}, \qquad q = \frac{T_n - T_{op}}{T_{op} - T_x}
$$

where:

- $f_T$ is the soil temperature factor (dimensionless),
- $T$ is the soil layer temperature (°C),
- $T_n$ is [tn](tn.md) (°C),
- $T_{op}$ is `top` (°C),
- $T_x$ is [tx](tx.md) (°C), and
- $q$ is the curve shape exponent (dimensionless).

[`fcgd.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/fcgd.f90#L14-L27) returns 0 when $T \le T_n$ or $T \ge T_x$. The function is used for decomposition when [tmpf](tmpf.md) `= 2` and for biological mixing unless `tmpf = 3`. Keep $T_n < T_{op} < T_x$.

The SWAT+ example file (`refdata/Ames_sub1`) heads this column `t_cbn_opt` and uses 30.0. The calibration parameter is `t_cbn_opt`.
