---
description: Land-phase nutrient soft-calibration flag.
---

# nut

**Code reference:** `cal_codes%nut` ([read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_read_codes.f90#L34), [gate](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_read_codes.f90#L39)).

Intended switch (`"y"` or `"n"`, struct default `"n"`) for land-phase nutrient soft calibration. Setting `nut = "y"` activates the overall `cal_soft = "y"` soft-calibration gate in [`calsoft_read_codes.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_read_codes.f90#L39), but no land-phase nutrient soft-calibration routine is implemented in SWAT+ main (`6f515368`).
