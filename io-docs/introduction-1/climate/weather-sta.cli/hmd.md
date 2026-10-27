---
description: Name of the relative humidity station
---

# hmd

**Code reference:** `wst(i)%wco_c%hgage`

**Declared type:** `weather_codes_station_char` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/cli_staread.f90#L68), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/climate_module.f90#L121)).

The name of the relative humidity station is a foreign key referencing the filenames listed in [**hmd.cli**](../hmd.cli-and-humidity-data-files.md).&#x20;

{% hint style="info" %}
If "sim" is entered instead of a relative humidity station name, the model will generate daily relative humidity values using the weather generator station specified in column [wgn](wgn.md).
{% endhint %}
