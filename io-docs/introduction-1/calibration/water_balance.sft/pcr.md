---
description: Target soil percolation ratio for soft calibration.
---

# pcr

**Code reference:** `lscal(ireg)%lum(ilum)%meas%pcr` ([read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/lcu_read_softcal.f90#L89), [calibration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_hyd.f90#L542-L630)).

Dimensionless target ratio of soil percolation to precipitation ($Q_{\text{perc}} / P$, struct default `0.`), used to calibrate `perco` in [`calsoft_hyd.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_hyd.f90#L542-L630) and [`caltsoft_hyd.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/caltsoft_hyd.f90#L340-L413).

In `b`/`y` mode (`hyd_hru /= "a"`), [`calsoft_hyd_bfr_et.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_hyd_bfr_et.f90#L45) and [`calsoft_hyd_bfr_et.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_hyd_bfr_et.f90#L114) combine `wyr` and `pcr` as $(f_{\text{wyr}} + f_{\text{pcr}}) P$ when calibrating `esco`.
