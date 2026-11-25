---
description: Number of months or years data is available for
---

# num\_aa

**Code reference:** `atmodep_cont%num` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/climate_module.f90#L214)).

{% hint style="info" %}
For monthly and yearly data, the number of months and number of years of atmospheric deposition data included in the file should be entered, respectively. For average annual data this parameter should be set to 0.
{% endhint %}

Monthly and yearly loads are applied only while the current deposition index is between 1 and this count. Average annual loads use the single value independently of this count. See [nut_nrain.f90](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/nut_nrain.f90#L42-L65).
