---
description: Probability of a wet day following a dry day in the month
---

# wet\_dry

**Code reference:** `wgn(iwgn)%pr_wd(mo)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/climate_module.f90#L36)).

The probability is calculated as

$$
P_i(W⁄D)=\frac{days_{W⁄D,i}}{days_{dry,i}}
$$

where $P_i(W⁄D)$ is the probability of a wet day following a dry day in month $i$, $days_{W⁄D,i}$ is the number of times a wet day followed a dry day in month $i$ for the entire period of record, and $days_{dry,i}$ is the number of dry days in month $i$ during the entire period of record. A dry day is a day with 0 mm of precipitation. A wet day is a day with > 0 mm precipitation.

If $p_{ww}\leq p_{wd}$ or $p_{wd}\leq 0$, SWAT+ replaces $p_{wd}$ as:

$$p_{wd} = \frac{0.75 \max(0.1, d_w)}{D}$$

where $p_{wd}$ is `wet_dry` (fraction), $p_{ww}$ is [wet\_wet](wet_wet.md) (fraction), $d_w$ is the supplied wet-day count (days), and $D$ is the number of days in the month (days). See [cli_initwgn.f90](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cli_initwgn.f90#L175-L188).
