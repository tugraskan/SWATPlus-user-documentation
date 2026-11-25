---
description: "Number identifying the demand object of the specified type"
---

# ob\_num

**Code reference:** `mallo(imro)%trn(i)%ob_num` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/manure_allocation_module.f90#L45), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/manure_allocation_read.f90#L94)).

Integer object number (default `0`) identifying the receiving object (for `ob_typ = "hru"`, the HRU index). Used to link `hru(ihru)%man_trn_dtbl` in [`manure_allocation_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/manure_allocation_read.f90#L99-L104) and to pass the HRU index to `conditions`, `actions`, and `pl_fert` in [`mallo_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mallo_control.f90#L42-L59).
