---
description: "Saturated hydraulic conductivity"
---

# soil_k

**Code reference:** `soil(j)%phys(ly)%k` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_module.f90#L38)).

Saturated hydraulic conductivity of the model layer. If the input is nonpositive, initialization uses 50, 20, 5, or 2 mm/h for hydrologic groups A, B, C, and D, respectively, or 10 mm/h for another group. [Model layer initialization](README.md#how-the-model-builds-the-printed-layers)

**Unit:** mm/h.

[Back to the output table](README.md).
