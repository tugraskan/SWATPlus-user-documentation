---
description: Percolation coefficient
---

# perco

**Code reference:** `hyd_db(ithyd)%perco`

**Declared type:** `hydrology_db` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/hydrol_read.f90#L47), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/hydrology_data_module.f90#L21)).

The percolation coefficient is input to limit percolation from the bottom soil layer due to an impermeable layer or high water table. Since percolation can be a slow process, that can occur over days or weeks, the percolation coefficient is non-linear and difficult to parameterize and calibrate.&#x20;

{% hint style="info" %}
A _perco_ value of 0.0 does not allow any percolation from the soil and a value of 1.0 does not restrict percolation from the bottom soil layer.
{% endhint %}

{% hint style="warning" %}

For an HRU with a tile drain, SWAT+ main (6f515368) sets perco to 0.1 during initialization, overriding the value entered in hydrology.hyd.

{% endhint %}
