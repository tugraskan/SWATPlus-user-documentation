---
description: "Plant uptake"
---

# uptake_kg/ha

**Code reference:** `hpestb_d(j)%pest(ipest)%pl_uptake` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_ls_pesticide_module.f90#L22)).

The daily root-uptake diagnostic sums pesticide removed from the soil by the plants and layers processed. It includes uptake for a pesticide configured as a terminal plant sink. That fraction is removed from soil without increasing the internal plant pool or the `harvest_sink` diagnostic. [Plant and layer loop](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pest_pl_up.f90#L45-L63), [Uptake and sink assignment](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pest_pl_up.f90#L101-L115).

**Unit:** kg/ha.

The same printed heading can appear in daily, monthly, yearly, and average-annual variants of this family. The reporting interval changes the row period; this page does not infer a total-versus-average rule beyond what the family output and source establish.

[Back to schema](hru-landscape-pesticide-balance.md).
