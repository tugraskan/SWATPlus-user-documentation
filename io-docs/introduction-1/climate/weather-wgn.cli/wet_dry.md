---
description: Probability of a wet day following a dry day in the month
---

# wet\_dry

**Code reference:** `wgn(iwgn)%pr_wd(mo)` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/climate_module.f90#L36)).

The probability is calculated as

$$
P_i(W⁄D)=\frac{days_{W⁄D,i}}{days_{dry,i}}
$$

where $$P_i(W⁄D)$$ is the probability of a wet day following a dry day in month $$i$$, $$days_{W⁄D,i}$$ is the number of times a wet day followed a dry day in month $$i$$ for the entire period of record, and $$days_{dry,i}$$ is the number of dry days in month $$i$$ during the entire period of record. A dry day is a day with 0 mm of precipitation. A wet day is a day with > 0 mm precipitation.
