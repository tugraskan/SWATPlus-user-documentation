---
description: Change type in ch_sed_parms.sft.
---

# chg\_typ

**Code reference:** `ch_prms(i)%chg_typ` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calibration_data_module.f90#L73), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_parms_cal.f90#L34)).

Intended change mode (`absval`, `abschg`, or `pctchg`, struct default `""`). In SWAT+ main (`6f515368`), only `ch_prms(1)%chg_typ` is echoed to `hru-new.cal` at [`calsoft_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_control.f90#L159); no calibration adjustment routine evaluates this field.
