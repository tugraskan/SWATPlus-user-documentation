---
description: Lignin fraction of below-ground residue
---

# bg\_lig\_frac

**Code reference:** `pldb(ic)%res_part_fracs%lig_frac`

**Declared type:** `residue_partition_fracs` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/plant_parm_read.f90#L57), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/plant_data_module.f90#L16)).

Used only when carbon in codes.bsn is set to 2. The model then derives the structural fraction (this value / 0.8) and the metabolic fraction (1 − structural) of below-ground residue from it. For other carbon settings this column is ignored.
