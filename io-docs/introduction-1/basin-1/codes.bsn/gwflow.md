---
description: GWFlow module switch
---

# gwflow

**Code reference:** `bsn_cc%gwflow` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L70), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_cc.f90#L24)).

Enables or disables the spatially distributed GWFlow groundwater module during object initialization ([`basin_read_objs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_objs.f90#L46-L83)) and simulation ([`command.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L659); struct default `0`).

| Code | Option |
| ---- | ------ |
| 0 | GWFlow module not active |
| 1 | GWFlow module active |

If `gwflow = 1` but `chancell.gw` is missing or empty, SWAT+ resets `bsn_cc%gwflow = 0` at runtime ([`basin_read_objs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_objs.f90#L74-L82)).
