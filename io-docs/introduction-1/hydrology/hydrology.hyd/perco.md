---
description: Percolation coefficient
---

# perco

The percolation coefficient is input to limit percolation from the bottom soil layer due to an impermeable layer or high water table. Since percolation can be a slow process, that can occur over days or weeks, the percolation coefficient is non-linear and difficult to parameterize and calibrate.&#x20;

{% hint style="info" %}
A _perco_ value of 0.0 does not allow any percolation from the soil and a value of 1.0 does not restrict percolation from the bottom soil layer.
{% endhint %}

{% hint style="warning" %}

For an HRU with a tile drain, SWAT+ main (6f515368) sets perco to 0.1 during initialization, overriding the value entered in hydrology.hyd.

{% endhint %}
