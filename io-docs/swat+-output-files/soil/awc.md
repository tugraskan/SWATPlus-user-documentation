---
description: "Available water capacity"
---

# awc

**Code reference:** `soil(j)%phys(ly)%awc` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_module.f90#L46)).

Available water capacity per unit thickness. Physical initialization sets values at or below `1.e-6` to 0.005 and caps values at 0.8. Field-capacity water depth and current water storage are separate model fields. [Model layer initialization](README.md#how-the-model-builds-the-printed-layers)

**Unit:** mm/mm.

[Back to the output table](README.md).
