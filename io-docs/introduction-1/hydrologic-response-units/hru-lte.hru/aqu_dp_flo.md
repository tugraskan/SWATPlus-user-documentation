---
description: Intended initial deep-aquifer storage (calibration handling and output only)
---

# aqu\_dp\_flo

**Code reference:** `hlt_db(i)%gwdeep` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_module.f90#L28)).

Intended initial deep-aquifer storage (mm), retained under the Editor field name `aqu_dp_flo`. SWAT+ main (6f515368) reads this value into `hlt_db%gwdeep` and handles and prints it during calibration, but does not copy it into the simulated deep-aquifer storage.

**Current use:** [storage declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_module.f90#L28); [calibration output](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_control.f90#L86).
