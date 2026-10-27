---
description: Number of years of maximum monthly 0.5 h rainfall data
---

# yrs\_pcp

**Code reference:** `wgn(iwgn)%rain_yrs`

**Declared type:** `weather_generator_db` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/cli_wgnread.f90#L91), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/climate_module.f90#L28)).

This variable is used to calculate values for [pcp\_hhr](pcp_hhr.md).&#x20;

{% hint style="info" %}
If no value is specified, the model will set _yrs\_pcp_ = 10.
{% endhint %}
