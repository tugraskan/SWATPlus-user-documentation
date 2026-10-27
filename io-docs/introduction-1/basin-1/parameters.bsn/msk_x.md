---
description: >-
  Weighting factor control relative importance of inflow rate and outflow rate
  in determining storage on reach
---

# msk\_x

**Code reference:** `bsn_prm%msk_x` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/basin_module.f90#L106)).

The weighting factor is a function of the wedge storage. This parameter is only important if channel routing is simulated using the Muskingum routing method.

{% hint style="info" %}
For reservoir-type storage, there is no wedge and _msk\_x_ should be 0.0. For a full-wedge, _msk\_x_ should be 0.5. For rivers, _msk\_x_ will fall between 0.0 and 0.3 with a mean value near 0.2.&#x20;
{% endhint %}
