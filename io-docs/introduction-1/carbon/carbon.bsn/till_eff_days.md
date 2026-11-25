---
description: "Number of days a tillage operation affects carbon cycling"
---

# till\_eff\_days

**Code reference:** `till_eff_days` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/tillage_data_module.f90#L6), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_bsn_read.f90#L74)).

Number of days after a tillage operation during which tillage still speeds up decomposition. When the days since tillage reach this value, [`hru_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_control.f90#L146-L154) ends the tillage effect and sets the tillage mixing factor of every layer to 0.

With [idc\_till](../../basin-1/codes.bsn/idc_till.md) `= 1`, [`cbn_zhang2.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cbn_zhang2.f90#L376-L390) also multiplies decomposition in the tilled layers by 1.6 while the days since tillage are no more than this value.

The SWAT+ example file (`refdata/Ames_sub1`) heads this column `till_eff_days` and uses 100.
