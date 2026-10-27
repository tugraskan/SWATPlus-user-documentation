---
description: Probability of a wet day following a wet day in the month
---

# wet\_wet

**Code reference:** `wgn(iwgn)%pr_ww(mo)` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/climate_module.f90#L37)).

The probability is calculated as

$$
P_i(W⁄W)=\frac{days_{W⁄W,i}}{days_{wet,i}}
$$

where $$P_i(W⁄W)$$ is the probability of a wet day following a wet day in month $$i$$, $$days_{W⁄W,i}$$ is the number of times a wet day followed a wet day in month $$i$$ for the entire period of record, and $$days_{wet,i}$$ is the number of wet days in month $$i$$ during the entire period of record. A wet day is a day with > 0 mm precipitation.
