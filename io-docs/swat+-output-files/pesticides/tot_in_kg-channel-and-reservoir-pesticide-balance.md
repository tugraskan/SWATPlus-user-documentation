---
description: "Total pesticide entering"
---

# tot_in_kg

**Code reference:** `chpst_d(j)%pest(ipest)%tot_in` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_pesticide_module.f90#L11)).

The incoming routed mass for the pesticide in the object's constituent hydrograph. It excludes the object's existing water and bed storage. Reservoirs that skip the daily pesticide routine can retain a prior diagnostic, and the basin rows sum object records, including transfers within the basin. [Channel input assignment](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_control3.f90#L441-L443), [Reservoir input and gate](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_pest.f90#L39-L49), [Basin reservoir sum](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_res_pest_output.f90#L23-L31).

**Unit:** kg.

The same printed heading can appear in daily, monthly, yearly, and average-annual variants of this family. The reporting interval changes the row period; this page does not infer a total-versus-average rule beyond what the family output and source establish.

[Back to schema](channel-reservoir-pesticide-balance.md).
