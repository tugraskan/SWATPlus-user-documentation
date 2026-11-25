---
description: Initial snow water equivalent
---

# snow\_h2o

**Code reference:** `hlt_db(i)%snow` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_module.f90#L29)).

This value is entered in mm. SWAT+ main (6f515368) reads it, but uses it only in calibration parameter handling and calibration output; it does not initialize the simulated HRU-lte snow water equivalent.
