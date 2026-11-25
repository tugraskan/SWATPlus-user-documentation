---
description: "Type of demand object receiving manure: hru for application"
---

# ob\_typ

**Code reference:** `mallo(imro)%trn(i)%ob_typ` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/manure_allocation_module.f90#L44), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/manure_allocation_read.f90#L94)).

Character string (`len=10`, default `""`) identifying the receiving demand object type (`hru` for HRU application; source comments also mention `muni` and `divert`). In SWAT+ main (`6f515368`), only `"hru"` is crosswalked to decision tables and application methods in [`manure_allocation_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/manure_allocation_read.f90#L98-L113), and `ob_typ` is echoed in demand output files ([`manure_demand_output.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/manure_demand_output.f90#L23)).
