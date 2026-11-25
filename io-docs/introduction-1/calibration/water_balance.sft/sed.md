---
description: Average annual land-phase sediment yield target for soft calibration.
---

# sed

**Code reference:** `lscal(ireg)%lum(ilum)%meas%sed` ([read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/lcu_read_softcal.f90#L89), [calibration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_sed.f90#L44-L185)).

Average annual land-phase sediment yield target (`t/ha`, struct default `0.`). When `sed = "y"` in `codes.sft`, [`calsoft_sed.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_sed.f90#L44-L185) adjusts HRU time of concentration (`tconc`, clamped to `[0, 1400]`) and slope (`slope`, clamped to `[1e-7, 2]`) to match this target.
