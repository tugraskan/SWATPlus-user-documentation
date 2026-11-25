---
description: "Manure type name referencing an entry in fertilizer.frt"
---

# manure\_typ

**Code reference:** `mallo(imro)%src(i)%manure_typ` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/manure_allocation_module.f90#L28), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/manure_allocation_read.f90#L67)).

Character string (`len=25`, default `""`) acting as a foreign key referencing [name](../../databases/fertilizer.frt/name_fertdb.md) in [**fertilizer.frt**](../../databases/fertilizer.frt/README.md). Matched against `fertdb%fertnm` in [`manure_allocation_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/manure_allocation_read.f90#L72-L77) to set `src(i)%fertdb`, which selects the nutrient composition applied via `pl_fert` in [`mallo_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mallo_control.f90#L55-L59).
