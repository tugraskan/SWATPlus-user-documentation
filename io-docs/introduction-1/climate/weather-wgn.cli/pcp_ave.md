---
description: Average or mean total monthly precipitation
---

# pcp\_ave

**Code reference:** `wgn(iwgn)%pcpmm(mo)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/climate_module.f90#L33)).

The average or mean total monthly precipitation is calculated as

$$
R_{mon}=\frac{∑_{d=1}^N*R_{day,mon}}{yrs}
$$

where $R_{mon}$ is the mean monthly precipitation (mm H2O), $R_{day,mon}$ is the daily precipitation for day $d$ in month $mon$ (mm H2O), $N$ is the total number of records in month $mon$ used to calculate the average, and $yrs$ is the number of years of daily precipitation records used in calculation.

SWAT+ divides monthly precipitation $P_m$ by the initialized number of wet days $d_w$ to obtain mean precipitation per wet day, $P_m/d_w$. See [cli_initwgn.f90](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cli_initwgn.f90#L187-L198).
