---
description: "Source type for general constituent concentrations (`const`, `dtbl`, or `recall`)"
---

# constit_typ

**Code reference:** `osrc(isrc)%conc(lev)%constit_typ` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L135), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_osrc_read.f90#L49-L52)).

6-character source type for general constituent concentrations (`const`, `dtbl`, or `recall`) for the outside water source (default: `""`). Only `org_min_typ` and `org_min_name` are crosswalked and evaluated in `6f515368`.

*(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations).*
