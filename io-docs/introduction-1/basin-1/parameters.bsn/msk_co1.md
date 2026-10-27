---
description: >-
  Coefficient to control the impact of the storage time constant for normal flow
  on the overall storage time constant for the channel
---

# msk\_co1

**Code reference:** `bsn_prm%msk_co1`

**Declared type:** `basin_parms` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/basin_read_prm.f90#L24), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/basin_module.f90#L100)).

Normal flow is defined as the streamflow when the channel is at bankfull depth. This parameter is only important if channel routing is simulated using the Muskingum routing method.
