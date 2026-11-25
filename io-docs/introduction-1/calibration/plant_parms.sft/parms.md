---
description: Number of calibrated plant parameters per land use in plant_parms.sft.
---

# parms

**Code reference:** `pl_prms(i)%parms` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calibration_data_module.f90#L167), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_read_parms_cal.f90#L48)).

Number of plant parameters per land use (struct default `2`). Used with `lum_num` in [`pl_read_parms_cal.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_read_parms_cal.f90#L78-L89) and [`pl_write_parms_cal.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_write_parms_cal.f90#L33) to compute the total parameter rows `lum_num * parms`.

Note that when `nspu > 0`, [`pl_read_parms_cal.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_read_parms_cal.f90#L52-L53) backspaces and omits `parms` on the re-read, so `parms` keeps whatever value was read on the first pass (or `2`).
