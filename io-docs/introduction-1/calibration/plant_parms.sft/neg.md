---
description: Lower iteration limit for a plant soft-calibration parameter.
---

# neg

**Code reference:** `pl_prms(i)%prm(ilum)%neg` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calibration_data_module.f90#L158), [clamp](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_plant.f90#L130-L502)).

Lower limit (real, struct default `0.`) constraining downward parameter steps during plant-growth soft calibration in [`calsoft_plant.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_plant.f90#L130-L502). When the updated calibration value drops to or below `neg`, it is clamped to `neg`.
