---
description: Dry weight of manure deposited daily
---

# man\_amt

**Code reference:** `grazeop_db(igrazop)%manure` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_operations_module.f90#L128), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_read_grazeops.f90#L49)).

Dry weight of manure deposited daily on the HRU during grazing (`(kg/ha)/day`; default `0.0`, valid range `0.0–500.0`).

On SWAT+ dev, when `man_amt > 0.` and [fert](fertnm.md) matched a [manure_db.frt](../../databases/manure_db.frt/README.md) record, [`pl_graze.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_graze.f90#L89-L96) applies the daily manure mass with `pl_manure`, all of it to the soil surface (surface fraction 1.0), using that manure record's composition, and records grazed N and P in `grazn` and `grazp`. (SWAT+ main used a fertilizer.frt record and added the masses to soil layer 1 directly.)
