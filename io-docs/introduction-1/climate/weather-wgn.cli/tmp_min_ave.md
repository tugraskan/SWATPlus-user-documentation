---
description: Average or mean daily minimum air temperature for month
---

# tmp\_min\_ave

**Code reference:** `wgn(iwgn)%tmpmn(mo)`

**Declared type:** `weather_generator_db` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/cli_wgnread.f90#L96), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/climate_module.f90#L30)).

This value is calculated by summing the minimum air temperature for every day in the month for all years of record and dividing the sum by the number of days:

$$
μmn_{mon}=\frac{∑_{d=1}^N*T_{mn,mon}}{N}
$$

where $$μmn_{mon}$$is the mean daily minimum temperature for the month $$mon$$ (ºC), $$T_{mn,mon}$$ is the daily minimum temperature on day $$d$$ in month $$mon$$ (ºC), and $$N$$is the total number of daily minimum temperature records for month $$mon$$.
