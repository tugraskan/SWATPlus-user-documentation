---
description: >-
  Start of growing season for non-tropical/start of monsoon initialization
  period for tropical
---

# grow\_start

**Code reference:** `hlt_db(i)%igrow1` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_module.f90#L37)).

Name of a decision table in [**lum.dtl**](../../decision-tables/lum.dtl/) that SWAT+ evaluates each day while no crop is growing ([`hru_lte_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_control.f90#L186-L192)). For non-tropical HRUs it is the start of the growing season (for example `pl_grow_sum`); for tropical HRUs, the start of the monsoon initialization period. SWAT+ writes a warning if the name is not found ([`hru_lte_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_read.f90#L167-L175)).

SWAT+ main (6f515368) also sums the HRU-lte potential heat units between the two entries' positions in `lum.dtl`, treating those positions as days of the year ([`hru_lte_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_read.f90#L188-L233)). Reordering the decision tables can therefore change the heat units.
