---
description: Negative change limit in ch_sed_parms.sft.
---

# neg

**Code reference:** `ch_prms(i)%neg` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calibration_data_module.f90#L74), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_parms_cal.f90#L34)).

Intended lower limit constraining downward parameter adjustments during channel sediment soft calibration (struct default `0.`).

*(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations).*
