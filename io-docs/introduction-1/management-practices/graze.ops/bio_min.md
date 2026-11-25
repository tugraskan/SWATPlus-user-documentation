---
description: Minimum plant biomass for grazing to occur
---

# grz\_bm\_min

**Code reference:** `grazeop_db(igrazop)%biomin` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_operations_module.f90#L129), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_read_grazeops.f90#L49)).

Minimum total above-ground plant community biomass (`kg/ha`; default `0.0`, valid range `0.0–5000.0`) required for grazing to occur on a given day.

In [`pl_graze.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_graze.f90#L38), if `pl_mass(j)%ab_gr_com%m < graze%biomin`, the subroutine returns immediately without removing plant biomass or depositing manure.
