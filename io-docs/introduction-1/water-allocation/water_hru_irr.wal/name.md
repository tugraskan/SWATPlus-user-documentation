---
description: "Irrigation-group name"
---

# name

**Code reference:** `hruirr_db(irr)%name` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L58), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_hru_irr_read.f90#L40)).

25-character name of the irrigation HRU group (default: `""`). Irrigation POUs in [place_of_use.wro](../place_of_use.wro/README.md) link to `hruirr_db` by integer `typ_num`, not by name.

*(Note: In SWAT+ main (6f515368) and dev (aa4179fe), this column is parsed into memory but is not used in simulation calculations).*
