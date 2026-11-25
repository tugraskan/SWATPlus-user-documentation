---
description: "Record name"
---

# name

**Code reference:** `osrc(isrc)%name` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L153), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_osrc_read.f90#L47)).

25-character name of the outside water source object (default: `""`). Outside sources are referenced by integer index via `typ_num` in [point_of_diver.wro](../point_of_diver.wro/README.md).

*(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations).*
