---
description: Average daily wind speed in month
---

# wnd\_ave

**Code reference:** `wgn(iwgn)%windav(mo)`

**Declared type:** `weather_generator_db` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/cli_wgnread.f90#L96), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/climate_module.f90#L42)).

This value is calculated by summing the average or mean wind speed values for every day in the month for all years of record and dividing the sum by the number of days:

$$
μwnd_{mon}=\frac{∑_{d=1}^N*T_{wnd,mon}}{N}
$$

where $$μwnd_{mon}$$ is the mean daily wind speed for the month (m/s), $$T_{wnd,mon}$$ is the average wind speed for day $$d$$ in month $$mon$$ (ºC), and _N_ is the total number of daily wind speed records for month $$mon$$.&#x20;
