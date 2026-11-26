---
description: "Record name"
---

# name

**Code reference:** `orcv(ircv)%name` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L171), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_orcv_read.f90#L45)).

25-character name of the outside-basin receiving object (default: `""`). Note that [`water_orcv_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_orcv_read.f90#L1-L54) is not called in SWAT+ main (`6f515368`).

*(Note: In SWAT+ main (6f515368) and dev (aa4179fe), this column is parsed into memory but is not used in simulation calculations).*
