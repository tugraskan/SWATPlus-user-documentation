---
description: Average lignin fraction of residue (read but not used)
---

# avg\_lig\_frac

**Code reference:** `lig_in%lig_frac_avg` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_data_module.f90#L10), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_parm_read.f90#L208-L218)).

Column 54, present only when [carbon](../../basin-1/codes.bsn/carbon.md) in codes.bsn is `2`. SWAT+ dev reads this value but does not use it.

With `carbon = 2` the three lignin columns are required: a line without them stops the run with an error naming the plant. Without carbon they must be left out: a number in column 54 stops the run ([`plant_parm_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_parm_read.f90#L244-L306)).
