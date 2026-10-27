---
description: Standard deviation for daily maximum air temperature in month
---

# tmp\_max\_sd

**Code reference:** `wgn(iwgn)%tmpstdmx(mo)`

**Declared type:** `weather_generator_db` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/cli_wgnread.f90#L96), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/climate_module.f90#L31)).

This parameter quantifies the variability in maximum temperature for each month. The standard deviation is calculated as

$$
σmx_{mon}=\sqrt{(\frac{∑_{d=1}^N*(T_{mx,mon}-μmx_{mon} )^2 }{N-1}})
$$

where $$σmx_{mon}$$is the standard deviation for daily maximum temperature in month $$mon$$ (ºC), $$T_{mx,mon}$$ is the daily maximum temperature on day $$d$$ in month $$mon$$ (ºC), $$μmx_{mon}$$ is the average daily maximum temperature for the month $$mon$$ (ºC), and $$N$$ is the total number of daily maximum temperature records for month $$mon$$.
