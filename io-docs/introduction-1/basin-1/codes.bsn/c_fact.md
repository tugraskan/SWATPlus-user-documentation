---
description: C-factor method selector (overwritten with 1 in main 6f515368)
---

# c\_fact

**Code reference:** `bsn_cc%cfac` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L43), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_cc.f90#L24)).

Legacy integer selector between the original SWAT minimum C-factor equation (`0`) and the APEX residue/biomass cover C-factor equation (`1`; struct default `0`).

On SWAT+ dev, [`ero_cfactor.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ero_cfactor.f90#L48-L80) no longer reads this flag: it always computes the C factor from each plant's residue and biomass cover, using [ero\_rsdfac](../../databases/plants.plt/ero_rsdfac.md) and [ero\_biofac](../../databases/plants.plt/ero_biofac.md) from plants.plt. The value entered here has no effect. (SWAT+ main overwrote it with 1 before testing it.)
