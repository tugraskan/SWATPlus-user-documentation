---
description: Target lateral soil flow ratio for soft calibration.
---

# lfr

**Code reference:** `lscal(ireg)%lum(ilum)%meas%lfr` ([read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/lcu_read_softcal.f90#L89), [calibration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_hyd.f90#L409-L481)).

Dimensionless target ratio of lateral soil flow to precipitation ($Q_{\text{lat}} / P$, struct default `0.`), used to calibrate `latq_co` in [`calsoft_hyd.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_hyd.f90#L409-L481) and [`calsoft_hyd_bfr_latq.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_hyd_bfr_latq.f90#L45-L118), and `revapc` for HRU-LTE in [`caltsoft_hyd.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/caltsoft_hyd.f90#L481-L551).

When `hyd_hru /= "a"` (`b` or `y` mode), [`lcu_read_softcal.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/lcu_read_softcal.f90#L96) overwrites the input value:

$$f_{\text{lfr}} = 0.1\,f_{\text{bfr}}'$$

where $f_{\text{lfr}}$ is the derived `lfr` target (dimensionless) and $f_{\text{bfr}}'$ is the converted baseflow fraction of precipitation (dimensionless).
