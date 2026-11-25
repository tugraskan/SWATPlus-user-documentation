---
description: Standard deviation for daily maximum air temperature in month
---

# tmp\_max\_sd

**Code reference:** `wgn(iwgn)%tmpstdmx(mo)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/climate_module.f90#L31)).

This parameter quantifies the variability in maximum temperature for each month. The standard deviation is calculated as

$$
σmx_{mon}=\sqrt{(\frac{∑_{d=1}^N*(T_{mx,mon}-μmx_{mon} )^2 }{N-1}})
$$

where $σmx_{mon}$ is the standard deviation for daily maximum temperature in month $mon$ (ºC), $T_{mx,mon}$ is the daily maximum temperature on day $d$ in month $mon$ (ºC), $μmx_{mon}$ is the average daily maximum temperature for the month $mon$ (ºC), and $N$ is the total number of daily maximum temperature records for month $mon$.

The standard deviation multiplies the generated maximum-temperature residual $Z_1$ in the term $\sigma_{\max} Z_1$. See [cli_tgen.f90](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cli_tgen.f90#L47-L49).
