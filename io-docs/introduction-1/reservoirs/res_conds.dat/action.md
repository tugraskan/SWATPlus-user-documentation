---
description: "Numeric action applied when this condition block is satisfied"
---

# action

**Code reference:** `ctbl(ictbl)%conds(ii)%action` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_conditions_module.f90#L19)).

Zero-based release module index selected when this top-level condition block is satisfied. In [`res_rel_conds.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_rel_conds.f90#L47-L48), SWAT+ selects which module in `ctbl(ictbl)%mods` is evaluated next using:

$$m = \text{int}(\text{action}) + 1$$

where $m$ is the 1-based release-module index (`modu`) and $\text{action}$ is `action` (dimensionless).
