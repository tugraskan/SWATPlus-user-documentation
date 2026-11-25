---
description: Target tile flow ratio for soft calibration.
---

# tfr

**Code reference:** `lscal(ireg)%lum(ilum)%meas%tfr` ([read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/lcu_read_softcal.f90#L89), [scale](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_control.f90#L52)).

Dimensionless target ratio of tile drainage flow to precipitation ($Q_{\text{tile}} / P$, struct default `0.`). Converted to mm (`precip_aa_sav * tfr`) in [`calsoft_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_control.f90#L52) and [`calsoft_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_control.f90#L72) for output summary reporting; no soft-calibration routine directly adjusts tile drainage parameters.
