---
description: "Chlorophyll-a component value in exco_om.exc"
---

# chla

**Code reference:** `exco(ii)%chla` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L38), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/exco_read_om.f90#L59)).

Constant chlorophyll-a mass (`kg`; Fortran default: `0.`). Copied into `ob(iob)%hd(1)` for standalone `exco` objects ([`exco_read_om.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/exco_read_om.f90#L83)), `recall(i)%hd(1,1)` for `type = 4` recalls ([`recall_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read.f90#L188)), and `outflo_om` in water allocation ([`wallo_start_day.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_start_day.f90#L82)), or scaled by `delrto` in routing units ([`ru_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_control.f90#L100)).
