---
description: Normal fraction of phosphorus in yield
---

# frac\_p\_yld

**Code reference:** `pldb(ic)%cpyld` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_data_module.f90#L56)).

{% hint style="warning" %}
On SWAT+ dev this column is not used: the seed phosphorus target is computed with the **nitrogen** yield fraction `cnyld` ([frac\_n\_yld](frac_n_yld.md)) instead of `cpyld` ([`pl_partition.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_partition.f90#L144-L154)). This comes from source reading.
{% endhint %}

In addition to the amount of plant biomass removed in the yield, SWAT+ needs to know the amount of nitrogen and phosphorus removed in the yield. The harvested portion of the plant biomass is sent to a testing laboratory to determine the fraction of nitrogen and phosphorus in the biomass.

This value is estimated on a dry weight basis.
