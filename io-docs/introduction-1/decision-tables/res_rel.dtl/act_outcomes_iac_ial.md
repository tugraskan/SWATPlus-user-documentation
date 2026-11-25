---
description: "Outcome flag for action iac and alternative ial (\"y\" to perform, \"n\" to skip)"
---

# act_outcomes(iac,ial)

**Code reference:** `dtbl_res(i)%act_outcomes(iac,ial)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditional_module.f90#L38)).

Supply one lowercase `y` or `n` per alternative. Each release row is eligible once if any satisfied alternative has `y`. The routine adds the eligible release contributions. With `alts = 0`, each action row is eligible without an outcome token. [`res_hydro.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_hydro.f90#L87-L106)
