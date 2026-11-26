---
description: Change type label in wb_parms.sft.
---

# chg\_typ

**Code reference:** `ls_prms(i)%chg_typ` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calibration_data_module.f90#L73), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ls_read_parms_cal.f90#L37)).

Documents the change mode (`absval`, `abschg`, or `pctchg`) for the parameter row. SWAT+ hardcodes additive or multiplicative updates in each soft-calibration subroutine rather than reading this field.

*(Note: In SWAT+ main (6f515368) and dev (aa4179fe), this column is parsed into memory but is not used in simulation calculations).*
