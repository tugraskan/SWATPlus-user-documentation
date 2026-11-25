---
description: "Depth to the bottom of the layer"
---

# soil_depth

**Code reference:** `soil(j)%phys(ly)%d` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_module.f90#L35)).

Cumulative depth from the surface to the bottom of the model layer. The writer truncates this depth to an integer. The model can add a 10 mm surface layer, use custom boundaries, or split a layer for a septic biozone. [Model layer initialization](README.md#how-the-model-builds-the-printed-layers)

**Unit:** mm.

[Back to the output table](README.md).
