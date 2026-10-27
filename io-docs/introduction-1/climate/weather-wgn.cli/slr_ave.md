---
description: Average daily solar radiation for month
---

# slr\_ave

**Code reference:** `wgn(iwgn)%solarav(mo)`

**Declared type:** `weather_generator_db` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/cli_wgnread.f90#L96), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/climate_module.f90#L40)).

This value is calculated by summing the total solar radiation for every day in the month for all years of record and dividing the sum by the number of days:

$$
μrad_{mon}=\frac{∑_{d=1}^N*H_{day,mon}}{N}
$$

where $$μrad_{mon}$$ is the mean daily solar radiation for the month (MJ/m2/day), $$H_{day,mon}$$ is the total solar radiation reaching the earth’s surface on day $$d$$ in month $$mon$$ (MJ/m2/day), and $$N$$ is the total number of daily solar radiation records for month $$mon$$.
