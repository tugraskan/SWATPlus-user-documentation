---
description: Elevation of the object
---

# elev

**Code reference:** `ob(i)%elev`

**Declared type:** `object_connectivity` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/hyd_read_connect.f90#L298), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/hydrograph_module.f90#L337)).

The elevation of HRUs is used to adjust precipitation and temperature when lapse rates are defined in [**parameters.bsn**](../../basin-1/parameters.bsn/) ([plaps](../../basin-1/parameters.bsn/s_max.md) and [tlaps](../../basin-1/parameters.bsn/n_fix.md)). The elevation of the remaining objects is not used by the model.&#x20;

{% hint style="warning" %}
Even though the elevation of most objects is not used by the model, a value has to be specified in the elevation column to make sure the file gets read correctly.&#x20;
{% endhint %}
