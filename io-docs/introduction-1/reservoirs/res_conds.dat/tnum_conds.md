---
description: "Number of condition entries in each release module"
---

# tnum\_conds

**Code reference:** `tnum_conds` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_read_conds.f90#L10)).

Number of condition entries defined inside a release module. In [`res_read_conds.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_read_conds.f90#L48-L50), SWAT+ allocates `ctbl(ictbl)%mods(imod)%con(tnum_conds)` and iterates over those entries in [`res_rel_conds.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_rel_conds.f90#L49).
