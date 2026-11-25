---
description: Skew coefficient for daily precipitation in month
---

# pcp\_skew

**Code reference:** `wgn(iwgn)%pcpskw(mo)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/climate_module.f90#L35)).

This parameter quantifies the symmetry of the precipitation distribution around the monthly mean. The skew coefficient is calculated as

$$
g_{mon}=\frac{N*∑_{d=1}^N*(R_{day,mon}-R_{mon})^3 }{(N-1)*(N-2)*(σ_{mon})^3}
$$

where:

- $g_{mon}$ is the skew coefficient for precipitation in the month (dimensionless),
- $N$ is the total number of daily precipitation records for month $mon$,
- $R_{day,mon}$ is the amount of precipitation for day $d$ in month $mon$ (mm H2O),
- $R_{mon}$ is the average precipitation for the month (mm H2O), and
- $σ_{mon}$ is the standard deviation for daily precipitation in month $mon$ (mm H2O).

Daily precipitation values of 0 mm are included in the skew coefficient calculation.

Skewness is dimensionless. Initialization clamps the input skew and the daily generator transforms a standard normal deviate:

$$g = \max(0.2, \, g_{\mathrm{input}}), \qquad r = \frac{g}{6}, \qquad X = \frac{2\left([1 + r(Z - r)]^3 - 1\right)}{g}$$

where:

- $g$ is the initialized skew coefficient (dimensionless),
- $g_{\mathrm{input}}$ is `pcp_skew` (dimensionless),
- $r$ is the intermediate skew parameter (dimensionless),
- $Z$ is a standard normal deviate (dimensionless), and
- $X$ is the transformed skew-adjusted deviate (dimensionless).

See [cli_pgen.f90](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cli_pgen.f90#L58-L63) and [cli_initwgn.f90](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cli_initwgn.f90#L193-L196).
