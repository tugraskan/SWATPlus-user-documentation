---
description: "Reaction loss and metabolite production"
---

# react_kg

**Code reference:** `aqupst_d(j)%pest(ipest)%react` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_pesticide_module.f90#L10)).

Reaction loss from the mass stored at the pesticide's turn plus the incoming recharge load. When temperature-adjusted decay is on, the aquifer passes 0 °C because the local temperature variable is initialized to zero and never updated. [Local temperature](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_1d_control.f90#L55-L59), [Decay and diagnostic](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_1d_control.f90#L309-L326).

**Unit:** kg.

The same printed heading can appear in daily, monthly, yearly, and average-annual variants of this family. The reporting interval changes the row period; this page does not infer a total-versus-average rule beyond what the family output and source establish.

[Back to schema](aquifer-pesticide-balance.md).
