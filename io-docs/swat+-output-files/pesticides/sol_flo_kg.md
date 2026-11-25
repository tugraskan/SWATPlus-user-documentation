---
description: "Dissolved and sorbed pesticide leaving with groundwater flow"
---

# sol_flo_kg

**Code reference:** `aqupst_d(j)%pest(ipest)%sol_flo` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_pesticide_module.f90#L7)).

The pesticide mass in the 1-D aquifer's return-flow hydrograph. The routine multiplies the mixed concentration by the groundwater flow depth, floors the mass at zero, and scales it alongside seepage if the combined export exceeds available mass. The companion `sor_flo_kg` field is zero. [Mixing and export](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_1d_control.f90#L339-L374).

**Unit:** kg.

The same printed heading can appear in daily, monthly, yearly, and average-annual variants of this family. The reporting interval changes the row period; this page does not infer a total-versus-average rule beyond what the family output and source establish.

[Back to schema](aquifer-pesticide-balance.md).
