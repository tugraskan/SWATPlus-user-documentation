---
description: Vegetation class of the plant (read but not used)
---

# vclass

**Code reference:** `pldb(ic)%vclass` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_data_module.f90#L97)).

Column 54 without carbon, 57 with `carbon = 2`. Vegetation class, up to 18 characters (for example row crop, close grown, vegetable, grassland, forest, orchard). SWAT+ dev reads it but no routine uses it. A file with the older 54-column layout gets `none`.
