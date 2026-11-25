---
description: >-
  Fraction used in year-end biomass mortality (not applied at dormancy)
---

# bm\_dieoff

**Code reference:** `pldb(ic)%bm_dieoff` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_data_module.f90#L82)).

Fraction used in the year-end mortality of biomass above [bm\_tree\_max](bm_tree_max.md): the removed mass is `(1 + bm_dieoff) × excess` ([`pl_mortality.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_mortality.f90#L24)). Values of `1e-6` or less are replaced by 1.0 ([`plantparm_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plantparm_init.f90#L18)).

Although described as die-off at dormancy, it does **not** remove biomass at dormancy in SWAT+ main (`6f515368`): the dormancy routine uses a fixed fraction of 0 ([`pl_dormant.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/pl_dormant.f90#L35-L39)).
