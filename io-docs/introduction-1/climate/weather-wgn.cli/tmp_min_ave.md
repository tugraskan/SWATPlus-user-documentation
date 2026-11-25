---
description: Average or mean daily minimum air temperature for month
---

# tmp\_min\_ave

**Code reference:** `wgn(iwgn)%tmpmn(mo)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/climate_module.f90#L30)).

This value is calculated by summing the minimum air temperature for every day in the month for all years of record and dividing the sum by the number of days:

$$
μmn_{mon}=\frac{∑_{d=1}^N*T_{mn,mon}}{N}
$$

where $μmn_{mon}$ is the mean daily minimum temperature for the month $mon$ (ºC), $T_{mn,mon}$ is the daily minimum temperature on day $d$ in month $mon$ (ºC), and $N$ is the total number of daily minimum temperature records for month $mon$.

The generator computes daily minimum temperature as $\mu_{\min}+\sigma_{\min}Z_2$. If the result exceeds the generated maximum $T_{\max}$, it sets the minimum to $T_{\max}-0.2|T_{\max}|$. See [cli_tgen.f90](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cli_tgen.f90#L42-L49).
