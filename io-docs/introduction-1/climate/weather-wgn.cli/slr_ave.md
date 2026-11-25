---
description: Average daily solar radiation for month
---

# slr\_ave

**Code reference:** `wgn(iwgn)%solarav(mo)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/climate_module.f90#L40)).

This value is calculated by summing the total solar radiation for every day in the month for all years of record and dividing the sum by the number of days:

$$
μrad_{mon}=\frac{∑_{d=1}^N*H_{day,mon}}{N}
$$

where $μrad_{mon}$ is the mean daily solar radiation for the month (MJ/m2/day), $H_{day,mon}$ is the total solar radiation reaching the earth’s surface on day $d$ in month $mon$ (MJ/m2/day), and $N$ is the total number of daily solar radiation records for month $mon$.

SWAT+ computes a daily solar-radiation estimate, then overwrites it with the monthly input mean $H_m$. On generated days the routine therefore returns $H_m$ in MJ/m²/day. See [cli_slrgen.f90](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cli_slrgen.f90#L30-L36).
