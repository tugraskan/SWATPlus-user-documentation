---
description: HRU-lte drainage area
---

# area

**Code reference:** `hlt_db(i)%dakm2` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_module.f90#L11)).

Drainage area in km². SWAT+ main (6f515368) converts HRU-lte water and sediment amounts with the object area from `hru-lte.con`, not with this value ([`hru_lte_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_control.f90#L351-L353)). This field is used in calibration output and in the fallback calculation for [t\_conc](t_conc.md) ([`hru_lte_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_read.f90#L247-L253)).
