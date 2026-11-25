---
description: "Decision table name for minimum POD level"
---

# dtbl_min (POD)

**Code reference:** `pou(ipou)%pod(ipod)%dtbl_min` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L21), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_read.f90#L97)).

25-character name of a decision table intended to set the minimum level of the POD for withdrawal (default: `""`). Neither crosswalked nor evaluated.

*(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations).*
