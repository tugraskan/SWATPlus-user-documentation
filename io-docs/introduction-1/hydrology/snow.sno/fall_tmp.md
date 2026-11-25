---
description: Snowfall temperature threshold
---

# fall\_tmp

**Code reference:** `snodb(isno)%falltmp` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_module.f90#L74)).

Mean daily air temperature threshold in °C. At or below this threshold, [`sq_snom.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sq_snom.f90#L51-L61) transfers effective precipitation to the snowpack as snowfall. The built-in snow record uses 0 °C.
