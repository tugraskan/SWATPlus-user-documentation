---
description: Probability of a wet day following a wet day in the month
---

# wet\_wet

**Code reference:** `wgn(iwgn)%pr_ww(mo)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/climate_module.f90#L37)).

The probability is calculated as

$$
P_i(W⁄W)=\frac{days_{W⁄W,i}}{days_{wet,i}}
$$

where $P_i(W⁄W)$ is the probability of a wet day following a wet day in month $i$, $days_{W⁄W,i}$ is the number of times a wet day followed a wet day in month $i$ for the entire period of record, and $days_{wet,i}$ is the number of wet days in month $i$ during the entire period of record. A wet day is a day with > 0 mm precipitation.

If $p_{ww}\leq p_{wd}$ or $p_{wd}\leq 0$, SWAT+ first replaces $p_{wd}$ and then sets:

$$p_{ww} = 0.25 + p_{wd}$$

where $p_{ww}$ is `wet_wet` (fraction) and $p_{wd}$ is [wet\_dry](wet_dry.md) (fraction). See [cli_initwgn.f90](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cli_initwgn.f90#L175-L188).
