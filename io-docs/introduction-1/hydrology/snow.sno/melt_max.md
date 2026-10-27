---
description: Melt factor for snow on June 21
---

# melt\_max

**Code reference:** `snodb(isno)%meltmx`

**Declared type:** `snow_parameters` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/snowdb_read.f90#L48), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/hru_module.f90#L76)).

The variables _melt\_max_ and [melt\_min](melt_min.md) allow the rate of snow melt to vary through the year and account for the impact of snowpack density on snow melt.&#x20;

If the watershed is in the Northern Hemisphere, _melt\_max_ will be the maximum melt factor. If the watershed is in the Southern Hemisphere, _melt\_max_ will be the minimum melt factor.&#x20;

{% hint style="info" %}
In rural areas, the melt factor will vary from 1.4 to 6.9 mm H2O/day-°C (Huber and Dickinson, 1988). In urban areas, values will fall in the higher end of the range due to compression of the snowpack by vehicles, pedestrians, etc. Urban snow melt studies in Sweden (Bengston, 1981; Westerstrom, 1981) reported melt factors ranging from 3.0 to 8.0 mm H2O/day-°C. Studies of snow melt on asphalt (Westerstrom, 1984) gave melt factors of 1.7 to 6.5 mm H2O/day-°C.
{% endhint %}
