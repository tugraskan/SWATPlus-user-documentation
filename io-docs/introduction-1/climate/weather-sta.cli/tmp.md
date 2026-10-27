---
description: Name of the temperature station
---

# tmp

**Code reference:** `wst(i)%wco_c%tgage` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/climate_module.f90#L119)).

The name of the temperature station is a foreign key referencing the filenames listed in [**tmp.cli**](../tmp.cli-and-temperature-data-files.md).&#x20;

{% hint style="info" %}
If "sim" is entered instead of a temperature station name, the model will generate daily temperature values using the weather generator station specified in column [wgn](wgn.md).
{% endhint %}
