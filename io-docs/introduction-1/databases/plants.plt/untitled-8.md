---
description: Maximum canopy height
---

# can\_ht\_max

**Code reference:** `pldb(ic)%chtmx` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_data_module.f90#L51)).

**Current use:** height increases with the square root of the leaf area curve value ([`pl_leaf_gro.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_leaf_gro.f90#L129-L133)).

Maximum canopy height is a straightforward measurement. The canopy height of non-stressed plants should be recorded at intervals throughout the growing season. The maximum value recorded is used in the database.
