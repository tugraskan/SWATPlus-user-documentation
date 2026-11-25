---
description: Optional crop name(s) for generic pl_hv decision tables
---

# auto\_crop

**Code reference:** `sched(isched)%auto_crop` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_operations_module.f90#L183), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_read_mgtops.f90#L72-L84)).

Optional trailing plant name(s) (`character(len=40)`) listed after [auto\_name](auto_name.md) when using SWAT+'s generic planting-harvest decision tables. In [`mgt_read_mgtops.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_read_mgtops.f90#L72-L84), SWAT+ reads one crop name for `pl_hv_summer1` or `pl_hv_winter1`, and two crop names for a two-year `pl_hv_summer2` rotation.

During `plant`, `harvest`, and `harvest_kill` decision-table actions ([`actions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L462-L468), [`#L505-L511`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L527-L533), [`#L621-L627`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L643-L649)), SWAT+ overrides the action's target crop option with `auto_crop(1)` (single-crop tables) or `auto_crop(pcom(j)%rot_yr)` (`pl_hv_summer2`).
