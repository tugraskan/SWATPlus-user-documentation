---
description: "Name identifying this component-value record"
---

# om_use_name

**Code reference:** `om_use_name(iom_use)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L218), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/om_use_read.f90#L44)).

16-character name identifying a water-use organic/mineral record. Matched against `org_min_name` in [water_use.wal](../water_use.wal/README.md) when `org_min_typ == "const"` ([`water_use_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_use_read.f90#L62)), and printed in water-use output files ([`wallo_use_output.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_use_output.f90#L19,L22,L35,L38,L53,L56,L71,L74)).
