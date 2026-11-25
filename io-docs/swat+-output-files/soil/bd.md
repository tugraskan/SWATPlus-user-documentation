---
description: "Bulk density"
---

# bd

**Code reference:** `soil(j)%phys(ly)%bd` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_module.f90#L37)).

Bulk density of the model layer. During physical initialization, values at or below `1.e-6` are set to 1.3 and values above 2.0 are capped at 2.0 Mg/m³. [Model layer initialization](README.md#how-the-model-builds-the-printed-layers)

**Unit:** Mg/m3.

[Back to the output table](README.md).
