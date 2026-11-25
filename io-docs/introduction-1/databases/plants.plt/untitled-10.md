---
description: Fraction of growing season when leaf area begins to decline
---

# hu\_lai\_decl

**Code reference:** `pldb(ic)%dlai` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_data_module.f90#L49)).

After this fraction of the heat units, annuals start losing leaf area ([`pl_leaf_senes.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_leaf_senes.f90#L34-L39)). Perennials with `temp_gro` start a 15-day leaf-drop period ([`pl_leaf_senes.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_leaf_senes.f90#L44-L53)). Leaf area growth also stops at this point ([`pl_leaf_gro.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_leaf_gro.f90#L114)).

Please see the explanation given for parameter [lai\_pot](untitled-15.md) to obtain additional information about this parameter and methods used to measure it.
