---
description: Threshold depth from surface to water table for revap to occur
---

# revap\_min

**Code reference:** `aqudb(i)%revap_min`

**Declared type:** `aquifer_database` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/aqu_read.f90#L55), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/aquifer_module.f90#L22)).

Movement of water from the aquifer to the unsaturated zone is allowed only if the depth from the surface to the water table is equal to or smaller than _revap\_min_.
