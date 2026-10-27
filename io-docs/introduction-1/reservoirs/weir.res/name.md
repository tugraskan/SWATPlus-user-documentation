---
description: Name of the reservoir weir record
---

# name (weir.res)

**Code reference:** `res_weir(ires)%name` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/reservoir_data_module.f90#L138)).

The name of the reservoir weir record is referenced by reservoir release actions whose option is `weir` in `res_rel.dtl`. It can also be referenced by a scheduled weir management operation. All names in `weir.res` must be unique.
