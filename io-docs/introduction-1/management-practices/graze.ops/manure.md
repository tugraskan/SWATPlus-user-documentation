---
description: Dry weight of manure deposited daily
---

# man\_amt

**Code reference:** `grazeop_db(igrazop)%manure` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_operations_module.f90#L128), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_read_grazeops.f90#L49)).

Dry weight of manure deposited daily on the HRU during grazing (`(kg/ha)/day`; default `0.0`, valid range `0.0–500.0`).

In [`pl_graze.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/pl_graze.f90#L86-L136), when `man_amt > 0.`, SWAT+ applies the daily manure mass to the surface soil layer (`l = 1`) using the mineral and organic N, P, and C fractions of the [**fertilizer.frt**](../../databases/fertilizer.frt/README.md) entry selected by [fert](fertnm.md), and records grazed N and P additions in `grazn` and `grazp` ([`pl_graze.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/pl_graze.f90#L95-L96)).
