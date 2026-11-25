---
description: Lignin fraction of above-ground residue
---

# ab\_lig\_frac

**Code reference:** `res_part_fracs(ic)%lig_frac_abg` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_data_module.f90#L11), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_parm_read.f90#L208-L218)).

Column 55, present only when [carbon](../../basin-1/codes.bsn/carbon.md) in codes.bsn is `2`. It sets the structural fraction of above-ground residue to this value / 0.8 and the metabolic fraction to the rest ([`plant_parm_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_parm_read.f90#L262-L278)). Residue transfers then split above-ground residue with it ([`cbn_rsd_transfer.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cbn_rsd_transfer.f90#L80)).

With `carbon = 2` the three lignin columns are required: a line without them stops the run with an error naming the plant. Without carbon they must be left out: a number in column 54 stops the run ([`plant_parm_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_parm_read.f90#L244-L306)).
