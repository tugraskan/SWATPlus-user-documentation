---
description: Fraction of hydrograph sent to the receiving object
---

# frac

**Code reference:** `ob(i)%frac_out(isp)`

**Declared type:** `object_connectivity` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/hyd_read_connect.f90#L298), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/hydrograph_module.f90#L371)).

{% hint style="warning" %}
When editing the fractions, the user has to make sure that they add up to 1. Otherwise, water will be added or removed from the system and the water balance will not close.
{% endhint %}
