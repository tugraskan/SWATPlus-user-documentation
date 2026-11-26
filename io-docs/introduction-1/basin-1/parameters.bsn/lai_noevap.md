---
description: Leaf area index above which soil evaporation ceases (read but not used in main 6f515368)
---

# lai\_noevap

**Code reference:** `bsn_prm%evlai` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L80), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_prm.f90#L24)).

Legacy leaf area index threshold above which soil evaporation does not occur (struct and runtime fallback default `3.0` when `< 1.e-6` in [`basin_prm_default.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_prm_default.f90#L9); exposed to calibration in [`cal_parm_select.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_parm_select.f90#L397)).

*(Note: In SWAT+ main (6f515368) and dev (aa4179fe), this column is parsed into memory but is not used in simulation calculations).*
