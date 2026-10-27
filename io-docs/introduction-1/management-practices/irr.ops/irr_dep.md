---
description: Currently not used in SWAT+ main (6f515368)
---

# dep\_sub

**Code reference:** `irrop_db(irr_op)%dep_mm`

**Declared type:** `irrigation_operation` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/mgt_read_irrops.f90#L48), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/mgt_operations_module.f90#L10)).


SWAT+ main (6f515368) reads this subsurface-irrigation depth from irr.ops but does not use the value afterward.
