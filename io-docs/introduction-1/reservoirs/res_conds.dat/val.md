---
description: "Value compared against the source variable"
---

# val

**Code reference:** `ctbl(ictbl)%conds(ii)%scon(icc)%val` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_conditions_module.f90#L14)).

Threshold value compared against [var](var.md) in [`res_rel_conds.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_rel_conds.f90#L28-L34). Units match the selected source variable ($\text{m}^3$ for `stor` and `inflo`; Julian day integer via `int(val)` when `var` is `day`).
