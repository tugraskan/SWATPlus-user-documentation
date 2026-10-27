---
description: Name of the wind speed station
---

# wnd

**Code reference:** `wst(i)%wco_c%wgage`

**Declared type:** `weather_codes_station_char` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/cli_staread.f90#L68), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/climate_module.f90#L122)).

The name of the wind speed station is a foreign key referencing the filenames listed in [**wnd.cli**](../wnd.cli-and-wind-speed-data-files.md).&#x20;

{% hint style="info" %}
If "sim" is entered instead of a wind speed station name, the model will generate daily wind speed values using the weather generator station specified in column [wgn](wgn.md).
{% endhint %}
