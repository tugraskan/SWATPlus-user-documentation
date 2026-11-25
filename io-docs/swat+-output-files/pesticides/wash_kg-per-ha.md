---
description: "Pesticide washed from foliage"
---

# wash_kg/ha

**Code reference:** `hpestb_d(j)%pest(ipest)%wash` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_ls_pesticide_module.f90#L19)).

Pesticide washed from the last qualifying plant in the daily wash-off loop. Each qualifying plant transfers its wash-off mass into the surface soil, and each assignment replaces the printed value. [Wash-off and report assignment](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pest_washp.f90#L26-L39).

**Unit:** kg/ha.

The same printed heading can appear in daily, monthly, yearly, and average-annual variants of this family. The reporting interval changes the row period; this page does not infer a total-versus-average rule beyond what the family output and source establish.

[Back to schema](hru-landscape-pesticide-balance.md).
