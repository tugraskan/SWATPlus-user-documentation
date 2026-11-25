---
description: Upper iteration limit for a plant soft-calibration parameter.
---

# pos

**Code reference:** `pl_prms(i)%prm(ilum)%pos` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calibration_data_module.f90#L159), [clamp](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_plant.f90#L125-L497)).

Upper limit (real, struct default `0.`) constraining upward parameter steps during plant-growth soft calibration in [`calsoft_plant.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_plant.f90#L125-L497). When the updated calibration value reaches or exceeds `pos`, it is clamped to `pos`.
