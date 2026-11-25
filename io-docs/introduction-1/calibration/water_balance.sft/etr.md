---
description: Target actual evapotranspiration ratio for soft calibration.
---

# etr

**Code reference:** `lscal(ireg)%lum(ilum)%meas%etr` ([read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/lcu_read_softcal.f90#L89), [calibration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_hyd.f90#L53-L201)).

Dimensionless target ratio of actual evapotranspiration to precipitation ($\text{ET} / P$, struct default `0.`), used to calibrate `esco` and `pet_co` in [`calsoft_hyd.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_hyd.f90#L53-L201) and `etco` for HRU-LTE in [`caltsoft_hyd.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/caltsoft_hyd.f90#L208-L278).
