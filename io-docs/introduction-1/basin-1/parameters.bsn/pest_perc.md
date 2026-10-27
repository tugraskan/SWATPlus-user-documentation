---
description: Pesticide percolation coefficient
---

# pest\_perc

**Code reference:** `bsn_prm%percop`

**Declared type:** `basin_parms` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/basin_read_prm.f90#L24), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/basin_module.f90#L99)).

This parameter controls the amount of pesticide removed from the surface layer in runoff and lateral flow relative to the amount removed via percolation. This parameter is only important if pesticide transport is simulated.&#x20;

{% hint style="info" %}
The lower _pest\_perc_, the lower the concentration of the pesticide in runoff. If _pest\_perc_ = 1.0, the surface runoff will have the same pesticide concentration as the percolate.
{% endhint %}
