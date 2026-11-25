---
description: "Dissolved and sorbed pesticide leaving with groundwater flow"
---

# sor_flo_kg

**Code reference:** `aqupst_d(j)%pest(ipest)%sor_flo` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_pesticide_module.f90#L8)).

In this output table, `sor_flo_kg` is one of the fields described as: Dissolved and sorbed pesticide leaving with groundwater flow.

**Unit:** kg.

The 1-D aquifer producer sets this field to zero and routes dissolved pesticide in `sol_flo_kg` and `sol_perc_kg`. [Output assignment](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_1d_control.f90#L369)

[Back to schema](aquifer-pesticide-balance.md).
