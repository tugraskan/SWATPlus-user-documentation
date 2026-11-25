---
description: Standard deviation for daily precipitation in month
---

# pcp\_sd

**Code reference:** `wgn(iwgn)%pcpstd(mo)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/climate_module.f90#L34)).

This parameter quantifies the variability in precipitation for each month. The standard deviation is calculated as

$$
σ_{mon}=\sqrt{(\frac{∑_{d=1}^N*(R_{day,mon}-R_{mon} )^2 }{N-1}})
$$

where $σ_{mon}$ is the standard deviation for daily precipitation in month $mon$ (mm H2O), $R_{day,mon}$ is the amount of precipitation for day $d$ in month $mon$ (mm H2O), $R_{mon}$ is the average precipitation for the month (mm H2O), and $N$ is the total number of daily precipitation records for month $mon$. Daily precipitation values of 0 mm are included in the standard deviation calculation.

The wet-day generator combines the skew-adjusted deviate $X$, this standard deviation $\sigma$, and the monthly wet-day mean $\mu$ as $\sigma X+\mu$ before applying the precipitation correction factor and floor. See [cli_pgen.f90](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cli_pgen.f90#L58-L64).
