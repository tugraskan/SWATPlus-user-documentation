---
description: Change type label in plant_parms.sft.
---

# chg\_typ

**Code reference:** `pl_prms(i)%prm(ilum)%chg_typ` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calibration_data_module.f90#L157), [output](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_write_parms_cal.f90#L54)).

Change mode label (`absval`, `abschg`, or `pctchg`, struct default `""`). [`calsoft_plant.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_plant.f90#L121-L516) applies hardcoded additive updates regardless of this column, and [`pl_write_parms_cal.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_write_parms_cal.f90#L54) only echoes the record structure to `plant_parms.cal`.

*(Note: In SWAT+ main (6f515368) and dev (aa4179fe), this column is parsed into memory but is not used in simulation calculations).*
