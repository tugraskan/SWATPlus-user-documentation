---
description: Standard deviation for daily minimum air temperature in month
---

# tmp\_min\_sd

**Code reference:** `wgn(iwgn)%tmpstdmn(mo)` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/climate_module.f90#L32)).

This parameter quantifies the variability in minimum temperature for each month. The standard deviation is calculated as

$$
σmn_{mon}=\sqrt{(\frac{∑_{d=1}^N*(T_{mn,mon}-μmn_{mon} )^2 }{N-1}})
$$

where $$σmn_{mon}$$is the standard deviation for daily minimum temperature in month $$mon$$ (ºC), $$T_{mn,mon}$$ is the daily minimum temperature on day $$d$$ in month $$mon$$ (ºC), $$μmn_{mon}$$ is the average daily minimum temperature for the month $$mon$$ (ºC), and $$N$$ is the total number of daily minimum temperature records for month $$mon$$.
