---
description: Average or mean total monthly precipitation
---

# pcp\_ave

**Code reference:** `wgn(iwgn)%pcpmm(mo)`

**Declared type:** `weather_generator_db` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/cli_wgnread.f90#L96), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/climate_module.f90#L33)).

The average or mean total monthly precipitation is calculated as

$$
R_{mon}=\frac{∑_{d=1}^N*R_{day,mon}}{yrs}
$$

where $$R_{mon}$$ is the mean monthly precipitation (mm H2O), $$R_{day,mon}$$ is the daily precipitation for day $$d$$ in month $$mon$$ (mm H2O), $$N$$ is the total number of records in month $$mon$$ used to calculate the average, and $$yrs$$ is the number of years of daily precipitation records used in calculation.
