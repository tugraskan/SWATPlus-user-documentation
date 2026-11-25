---
description: Biomass cover factor in the USLE C factor equation
---

# ero\_biofac

**Code reference:** `pldb(ic)%ero_biofac` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_data_module.f90#L96)).

Column 53. Weight of growing above-ground biomass in the daily USLE C factor; see the equation on [ero\_rsdfac](ero_rsdfac.md). The source default is 0.2.

{% hint style="warning" %}
Unlike the other new columns, a value ≤ 0 is not replaced: the default check meant for this column tests `ero_rsdfac` a second time ([`plantparm_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plantparm_init.f90#L30-L31)). A 0 removes the biomass term from the C factor. This comes from source reading.
{% endhint %}

In SWAT+ main this column held `rsd_covfac`, which was read but had no effect. A file with the older 54-column layout gets the default 0.2 here.
