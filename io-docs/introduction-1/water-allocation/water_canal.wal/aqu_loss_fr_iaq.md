---
description: "Seepage fraction assigned to each aquifer"
---

# aqu_loss_fr(iaq)

**Code reference:** `canal(ic)%aqu_loss_fr(iaq)` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/water_allocation_module.f90#L211)).

Supply one fraction for each aquifer counted by [num_aqu](num_aqu.md), at the end of the same canal row. The values correspond to aquifer indices 1 through num_aqu in that order. There is no separate aquifer identifier column.
