---
description: "Pesticide stored in water and benthic sediment"
---

# water_stor_kg

**Code reference:** `chpst_d(j)%pest(ipest)%water` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_pesticide_module.f90#L23)).

Daily pesticide mass remaining in the water compartment after the active pesticide routine subtracts export. A reservoir with 1 m³ or less of remaining water skips the routine and can repeat the last stored diagnostic. [Channel storage](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_rtpest.f90#L246-L251), [Reservoir gate](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_pest.f90#L39-L49), [Reservoir storage](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_pest.f90#L189-L203).

**Unit:** kg.

The same printed heading can appear in daily, monthly, yearly, and average-annual variants of this family. The reporting interval changes the row period; this page does not infer a total-versus-average rule beyond what the family output and source establish.

[Back to schema](channel-reservoir-pesticide-balance.md).
