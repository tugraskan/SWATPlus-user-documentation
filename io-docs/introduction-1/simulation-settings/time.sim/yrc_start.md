---
description: Beginning year of the simulation
---

# yrc\_start

**Code reference:** `time%yrc_start`

**Declared type:** `time_current` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/time_read.f90#L28), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/time_module.f90#L22)).

{% hint style="info" %}
If the simulation begins before the first day of the observed climate data, SWAT+ will use simulated climate data for the time period before the start of the observed climate data.
{% endhint %}
