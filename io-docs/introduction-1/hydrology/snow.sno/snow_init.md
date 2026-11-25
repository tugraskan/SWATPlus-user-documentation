---
description: Initial snow water equivalent
---

# snow\_init

**Code reference:** `snodb(isno)%init_mm` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_module.f90#L81)).

Initial snow water equivalent on the HRU in mm at the start of the simulation. [`topohyd_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/topohyd_init.f90#L88-L90) copies the value from the selected snow record to HRU snow storage. The built-in record uses 0 mm.
