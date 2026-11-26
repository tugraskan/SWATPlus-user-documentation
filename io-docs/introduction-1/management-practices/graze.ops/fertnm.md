---
description: Fertilizer name for manure deposited during grazing
---

# fert

**Code reference:** `grazeop_db(igrazop)%fertnm` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_operations_module.f90#L124), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_read_grazeops.f90#L49)).

The fertilizer name for manure deposited during grazing is a foreign key referencing [name](../../databases/fertilizer.frt/name_fertdb.md) in [**fertilizer.frt**](../../databases/fertilizer.frt/README.md).

On SWAT+ dev, [`mgt_read_grazeops.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_read_grazeops.f90#L53-L61) matches `fertnm` against the names in [manure_db.frt](../../databases/manure_db.frt/README.md) (not fertilizer.frt) and stores the matching index in `grazeop_db(igrazop)%manure_id`. During simulation, [`pl_graze.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_graze.f90#L89-L96) applies the deposited manure with the same routine as the `manu` operation, using that manure record's composition. A name with no match leaves the index at 0 and no manure is applied. (SWAT+ main matched against fertilizer.frt.)
