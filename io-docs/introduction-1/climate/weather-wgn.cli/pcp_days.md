---
description: Average number of days of precipitation in month
---

# pcp\_days

**Code reference:** `wgn(iwgn)%pcpd(mo)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/climate_module.f90#L38)).

This parameter is calculated as

$$
d_{wet,i}=\frac{days_{wet,i}}{yrs}
$$

where $d_{wet,i}$ is the average number of days of precipitation in month $i$, $days_{wet,i}$ is the number of wet days in month $i$ during the entire period of record, and $yrs$ is the number of years of record.

If the input transition probabilities require replacement, SWAT+ first floors the input wet-day count at 0.1 and uses it to estimate them. It then sets the working wet-day count to $D p_{wd}/(1-p_{ww}+p_{wd})$, where $D$ is the number of days in the month. Nonpositive results are set to 0.001. See [cli_initwgn.f90](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cli_initwgn.f90#L175-L198).
