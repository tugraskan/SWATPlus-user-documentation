---
description: "Outcome flag for action iac under alternative ial (\"y\" performs the action, \"n\" does not)"
---

# act_outcomes(iac,ial)

**Code reference:** `dtbl_scen(i)%act_outcomes(iac,ial)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditional_module.f90#L38)).

Supply one lowercase `y` or `n` per alternative. In the general action evaluator, the action row is eligible once if any satisfied alternative has `y` for that row. Each action row is considered separately, so more than one action can run. [`actions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L99-L109)
