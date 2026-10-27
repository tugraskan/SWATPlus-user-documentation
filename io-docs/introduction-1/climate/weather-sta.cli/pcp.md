---
description: Name of the precipitation station
---

# pcp

**Code reference:** `wst(i)%wco_c%pgage` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/climate_module.f90#L118)).

The name of the precipitation station is a foreign key referencing the filenames listed in [**pcp.cli**](../pcp.cli-and-precipitation-data-files.md).&#x20;

{% hint style="info" %}
If "sim" is entered instead of a precipitation station name, the model will generate daily precipitation values using the weather generator station specified in column [wgn](wgn.md).
{% endhint %}
