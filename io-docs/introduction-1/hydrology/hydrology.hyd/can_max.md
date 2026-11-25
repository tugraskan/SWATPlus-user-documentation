---
description: Maximum canopy storage
---

# can\_max

**Code reference:** `hyd_db(ithyd)%canmx` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrology_data_module.f90#L10)).

Maximum canopy water storage, in mm, at maximum leaf area. For daily and subdaily rainfall, [`sq_canopyint.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sq_canopyint.f90#L45-L53) scales the storage capacity as:

$$C = C_{\max} \frac{\operatorname{LAI}}{\operatorname{LAI}_{\max}}$$

where $C$ is the current canopy storage capacity (mm), $C_{\max}$ is `can_max` (mm), $\operatorname{LAI}$ is the current leaf area index, and $\operatorname{LAI}_{\max}$ is the maximum leaf area index. The routine skips interception if either leaf-area index total is below 0.001. Daily precipitation first fills available canopy storage. [`sq_canopyint.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sq_canopyint.f90#L80-L88)
