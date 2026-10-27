---
description: Nitrate percolation coefficient
---

# n\_perc

**Code reference:** `bsn_prm%nperco`

**Declared type:** `basin_parms` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/basin_read_prm.f90#L24), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/basin_module.f90#L90)).

This parameter controls the amount of nitrate removed from the surface layer in runoff relative to the amount removed via percolation.

{% hint style="info" %}
The smaller _n\_perc_, the lower the concentration of nitrate in runoff. If _n\_perc_ = 1.0, the surface runoff will have the same nitrate concentration as the percolate.
{% endhint %}
