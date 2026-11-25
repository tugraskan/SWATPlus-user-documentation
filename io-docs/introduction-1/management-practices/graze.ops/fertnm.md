---
description: Fertilizer name for manure deposited during grazing
---

# fert

**Code reference:** `grazeop_db(igrazop)%fertnm` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_operations_module.f90#L124), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_read_grazeops.f90#L49)).

The fertilizer name for manure deposited during grazing is a foreign key referencing [name](../../databases/fertilizer.frt/name_fertdb.md) in [**fertilizer.frt**](../../databases/fertilizer.frt/README.md).

During input processing, [`mgt_read_grazeops.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/mgt_read_grazeops.f90#L55-L56) matches `fertnm` against `fertdb(ifert)%fertnm` and stores the matching index in `grazeop_db(igrazop)%manure_id`. During simulation, [`pl_graze.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/pl_graze.f90#L85-L136) uses that record to determine the mineral and organic N, P, and C fractions of manure deposited when `man_amt > 0`.
