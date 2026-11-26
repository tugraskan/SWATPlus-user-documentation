---
description: "Weather station name"
---

# w_sta

**Code reference:** `canal(ic)%w_sta` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L193), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_canal_read.f90#L44,L53)).

25-character name of a nearby weather station (default: `""`). The weather-station crosswalk in [`water_canal_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_canal_read.f90#L61) is an empty comment.

*(Note: In SWAT+ main (6f515368) and dev (aa4179fe), this column is parsed into memory but is not used in simulation calculations).*
