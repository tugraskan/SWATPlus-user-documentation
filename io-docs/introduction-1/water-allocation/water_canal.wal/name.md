---
description: "Canal name"
---

# name

**Code reference:** `canal(ic)%name` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L192), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_canal_read.f90#L44,L53)).

25-character name of the canal (default: `""`). Canals are referenced by integer index in [place_of_use.wro](../place_of_use.wro/README.md) and [point_of_diver.wro](../point_of_diver.wro/README.md).

*(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations).*
