---
description: Average or mean daily maximum air temperature for month
---

# tmp\_max\_ave

**Code reference:** `wgn(iwgn)%tmpmx(mo)` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/climate_module.f90#L29)).

This value is calculated by summing the maximum air temperature for every day in the month for all years of record and dividing the sum by the number of days:

$$
μmx_{mon}=\frac{∑_{d=1}^N*T_{mx,mon}}{N}
$$

where $$μmx_{mon}$$is the mean daily maximum temperature for the month $$mon$$ (ºC), $$T_{mx,mon}$$ is the daily maximum temperature on day $$d$$ in month $$mon$$ (ºC), and $$N$$is the total number of daily maximum temperature records for month $$mon$$.
