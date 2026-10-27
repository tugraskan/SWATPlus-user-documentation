---
description: >-
  Average daily dew point temperature for each month (ºC) or relative humidity
  (fraction)
---

# dew\_ave

**Code reference:** `wgn(iwgn)%dewpt(mo)`

**Declared type:** `weather_generator_db` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/cli_wgnread.f90#L96), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/climate_module.f90#L41)).

If all twelve months are < 1.0, the model assumes the data provided is relative humidity. Relative humidity is defined as the amount of water vapor in the air as a fraction of saturation humidity. If any month has a value > 1.0, the model assumes the data provided is dewpoint temperature.

Dew point temperature is the temperature at which the actual vapor pressure present in the atmosphere is equal to the saturation vapor pressure. This value is calculated by summing the dew point temperature for every day in the month for all years of record and dividing the sum by the number of days:

$$
μdew_{mon}=\frac{∑_{d=1}^N*T_{dew,mon}}{N}
$$

where $$μdew_{mon}$$ is the mean daily dew point temperature for the month (ºC), $$T_{dew,mon}$$ is the dew point temperature for day $$d$$ in month $$mon$$ (ºC), and $$N$$is the total number of daily dew point records for month $$mon$$. Please refer to the SWAT+ Theoretical Documentation for the equations used to convert dew point to relative humidity.&#x20;
