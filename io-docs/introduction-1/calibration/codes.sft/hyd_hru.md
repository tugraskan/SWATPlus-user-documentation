---
description: HRU water balance soft-calibration mode switch.
---

# hyd\_hru

**Code reference:** `cal_codes%hyd_hru` ([read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_read_codes.f90#L34), [dispatch](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_control.f90#L38-L39)).

Selects the HRU water-balance soft-calibration mode (struct default `"n"`). When `"n"`, HRU water-balance soft calibration is disabled. When `"a"`, SWAT+ calibrates all HRU hydrologic processes against `srr`, `lfr`, `pcr`, and `etr` from `water_balance.sft` in [`calsoft_hyd.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_hyd.f90#L53-L815).

Any value other than `"n"` and `"a"` (for example `"b"` or `"y"`) selects baseflow-ratio mode in [`calsoft_hyd_bfr.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_hyd_bfr.f90#L1-L65) and causes [`lcu_read_softcal.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/lcu_read_softcal.f90#L92-L96) to derive `srr`, `bfr`, and `lfr` from `wyr` and `bfr`. Note that [`caltsoft_hyd.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/caltsoft_hyd.f90#L767) resets `cal_codes%hyd_hru = "n"` when HRU-LTE soft calibration finishes.
