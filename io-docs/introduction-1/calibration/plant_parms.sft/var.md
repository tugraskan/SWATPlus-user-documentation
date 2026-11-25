---
description: Plant parameter variable name in plant_parms.sft.
---

# var

**Code reference:** `pl_prms(i)%prm(ilum)%var` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calibration_data_module.f90#L154), [dispatch](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_read_parms_cal.f90#L95-L103)).

Plant parameter variable name (up to 16 characters, struct default `"default"`). Supported names in [`pl_read_parms_cal.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_read_parms_cal.f90#L95-L103) and [`pl_write_parms_cal.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_write_parms_cal.f90#L35-L51) are `epco`, `pest_stress`, `lai_pot`, and `harv_idx`.

During iteration, [`calsoft_plant.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_plant.f90#L93-L516) accesses rows by fixed block offset (`ilum`, `ilum + nvar`, `ilum + 2*nvar`, `ilum + 3*nvar`), expecting blocks ordered `pest_stress`, `epco`, `lai_pot`, `harv_idx`.
