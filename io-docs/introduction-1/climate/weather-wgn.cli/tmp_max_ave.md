---
description: Average or mean daily maximum air temperature for month
---

# tmp\_max\_ave

**Code reference:** `wgn(iwgn)%tmpmx(mo)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/climate_module.f90#L29)).

This value is calculated by summing the maximum air temperature for every day in the month for all years of record and dividing the sum by the number of days:

$$
μmx_{mon}=\frac{∑_{d=1}^N*T_{mx,mon}}{N}
$$

where $μmx_{mon}$ is the mean daily maximum temperature for the month $mon$ (ºC), $T_{mx,mon}$ is the daily maximum temperature on day $d$ in month $mon$ (ºC), and $N$ is the total number of daily maximum temperature records for month $mon$.

The generator starts from the monthly maximum temperature mean, adds half the monthly temperature range times the wet-day probability, and removes that half-range on wet days. It adds $\sigma_{\max}Z_1$, where $\sigma_{\max}$ is the monthly maximum-temperature standard deviation and $Z_1$ is the generated temperature residual. See [cli_tgen.f90](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cli_tgen.f90#L42-L49).
