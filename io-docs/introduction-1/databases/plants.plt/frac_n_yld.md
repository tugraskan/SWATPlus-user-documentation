---
description: Normal fraction of nitrogen in yield
---

# frac\_n\_yld

**Code reference:** `pldb(ic)%cnyld` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_data_module.f90#L55)).

**Current use:** on SWAT+ dev, N taken up each day first tops the seed (yield) nitrogen up toward `frac_n_yld × seed mass`, limited by the N available ([`pl_partition.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_partition.f90#L106-L116)).

In addition to the amount of plant biomass removed in the yield, SWAT+ needs to know the amount of nitrogen and phosphorus removed in the yield. The harvested portion of the plant biomass is sent to a testing laboratory to determine the fraction of nitrogen and phosphorus in the biomass.

This value is estimated on a dry weight basis.
