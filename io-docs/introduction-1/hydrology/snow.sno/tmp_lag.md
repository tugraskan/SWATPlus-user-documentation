---
description: Snowpack temperature lag factor
---

# tmp\_lag

**Code reference:** `snodb(isno)%timp`

**Declared type:** `snow_parameters` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/snowdb_read.f90#L48), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/hru_module.f90#L78)).

The influence of the previous day’s snowpack temperature on the current day’s snow pack temperature is controlled by a lagging factor, which inherently accounts for snow pack density, snowpack depth, exposure and other factors affecting snowpack temperature.&#x20;

{% hint style="info" %}
As _tmp\_lag_ approaches 1.0, the mean air temperature on the current day exerts an increasingly greater influence on the snow pack temperature and the snow pack temperature from the previous day exerts less and less influence. As it approaches zero, the snowpack temperature will be less influenced by the current day's air temperature.
{% endhint %}
