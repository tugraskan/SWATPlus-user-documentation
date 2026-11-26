---
description: "Initial concentration-set name"
---

# init

**Code reference:** `canal(ic)%init` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L194), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_canal_read.f90#L44,L53)).

25-character name of the initial concentration set in the canal (default: `""`). The initial-concentration crosswalk in [`water_canal_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_canal_read.f90#L63) is an empty comment.

*(Note: In SWAT+ main (6f515368) and dev (aa4179fe), this column is parsed into memory but is not used in simulation calculations).*
