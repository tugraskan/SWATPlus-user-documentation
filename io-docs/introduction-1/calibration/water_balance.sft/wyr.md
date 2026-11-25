---
description: Target total water yield ratio for baseflow-mode soft calibration.
---

# wyr

**Code reference:** `lscal(ireg)%lum(ilum)%meas%wyr` ([read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/lcu_read_softcal.f90#L89), [conversion](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/lcu_read_softcal.f90#L94-L95)).

Dimensionless target ratio of total water yield to precipitation ($\text{WYLD} / P$, struct default `0.`). Used when `hyd_hru /= "a"` (`b` or `y` mode) in [`lcu_read_softcal.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/lcu_read_softcal.f90#L94-L95) to compute `srr` and `bfr`, and in [`calsoft_hyd_bfr_et.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_hyd_bfr_et.f90#L45) and [`calsoft_hyd_bfr_pet.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_hyd_bfr_pet.f90#L39) to calibrate `esco` and `pet_co`.
