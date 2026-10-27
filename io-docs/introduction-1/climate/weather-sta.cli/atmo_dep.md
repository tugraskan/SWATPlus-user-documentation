---
description: Name of the atmospheric deposition station
---

# atmo\_dep

**Code reference:** `wst(i)%wco_c%atmodep`

**Declared type:** `weather_codes_station_char` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/cli_staread.f90#L68), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/climate_module.f90#L124)).

The name of the atmospheric deposition station is a foreign key referencing the station names in [atmo.cli](../atmo.cli/).&#x20;

{% hint style="info" %}
If no atmospheric deposition data are available, "null" should be entered instead of an atmospheric deposition station name.
{% endhint %}
