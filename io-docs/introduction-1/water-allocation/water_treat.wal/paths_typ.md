---
description: "Source type for pathogen concentrations (`const`, `dtbl`, or `recall`)"
---

# paths_typ

**Code reference:** `wtp(iwtp)%conc(lev)%paths_typ` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L132), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_treatment_read.f90#L52-L55)).

6-character source type for pathogen concentrations (`const`, `dtbl`, or `recall`) for the water treatment plant (default: `""`). Only `org_min_typ` and `org_min_name` are crosswalked and evaluated in `6f515368`.

*(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations).*
