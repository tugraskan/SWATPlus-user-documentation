---
description: "Name of the pathogen source record"
---

# paths_name

**Code reference:** `osrc(isrc)%conc(lev)%paths_name` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L138), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_osrc_read.f90#L49-L52)).

25-character name of the pathogen source record for the outside water source (default: `""`). Only `org_min_typ` and `org_min_name` are crosswalked and evaluated in `6f515368`.

*(Note: In SWAT+ main (6f515368) and dev (aa4179fe), this column is parsed into memory but is not used in simulation calculations).*
