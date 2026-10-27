---
description: Name of the solar radiation station
---

# slr

**Code reference:** `wst(i)%wco_c%sgage`

**Declared type:** `weather_codes_station_char` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/cli_staread.f90#L68), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/climate_module.f90#L120)).

The name of the solar radiation station is a foreign key referencing the filenames listed in [**slr.cli**](../slr.cli-and-solar-radiation-data-files.md).&#x20;

{% hint style="info" %}
If "sim" is entered instead of a solar radiation station name, the model will generate daily solar radiation values using the weather generator station specified in column [wgn](wgn.md).
{% endhint %}
