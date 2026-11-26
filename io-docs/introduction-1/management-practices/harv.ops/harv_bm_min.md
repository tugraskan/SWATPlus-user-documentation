---
description: Minimum biomass to allow harvest
---

# harv\_bm\_min

**Code reference:** `harvop_db(iharvop)%bm_min` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_operations_module.f90#L116), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_read_harvops.f90#L44)).

Minimum plant or residue biomass (`kg/ha`; default `0.0`, non-negative) required for harvest or to remain after residue harvest. SWAT+ evaluates `harv_bm_min` in three places:

1. **Harvest execution gate:** Scheduled and decision-table harvest actions check `biomass > harv_bm_min` before executing in [`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L164) / [`#L276`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L276) and [`actions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L540) / [`#L634`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L656).
2. **Biomass harvest post-yield check:** In [`mgt_harvbiomass.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_harvbiomass.f90#L49), yield is set to zero unless remaining above-ground biomass satisfies `pl_mass(j)%ab_gr(ipl)%m - pl_yield%m > harv_bm_min`.
3. **Residue harvest floor:** In [`mgt_harvresidue.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_harvresidue.f90#L61-L73), SWAT+ dev harvests the surface residue of the plant being harvested only when it exceeds `1.e-6` kg/ha. If removal would leave less than `harv_bm_min`, the removed fraction becomes $\max(0, (M_{\text{rsd}} - B_{\text{min}}) / M_{\text{rsd}})$, so residue already below the floor is not removed. (On SWAT+ main the fraction could become negative and add residue.)
