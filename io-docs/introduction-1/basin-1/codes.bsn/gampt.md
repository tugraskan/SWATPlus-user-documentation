---
description: Surface runoff method
---

# gampt

**Code reference:** `bsn_cc%gampt` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L65), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_cc.f90#L24)).

Selects between the SCS Curve Number and Green & Ampt infiltration/runoff methods in [`sq_volq.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sq_volq.f90#L23), [`sq_surfst.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sq_surfst.f90#L45), [`ru_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_control.f90#L230), and [`hru_hyds.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_hyds.f90#L195) (struct default `0`).

| Code | Option |
| ---- | ------ |
| 0 | Curve Number |
| 1 | Green & Ampt |

Green & Ampt (`gampt = 1`) requires sub-daily rainfall (`step > 1` in [**time.sim**](../../simulation-settings/time.sim/)) and activates urban impervious initial abstraction ([urb\_init\_abst](../parameters.bsn/urb_init_abst.md)) as well as splash and overland-flow erosion in [`ero_ovrsed.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ero_ovrsed.f90#L133).
