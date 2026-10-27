---
description: Particulate P removal by BMP
---

# ptlp\_eff

**Code reference:** `bmpuser_db(ibmpop)%bmp_pp` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/mgt_operations_module.f90#L63)).

Enter the fraction of particulate phosphorus removed by this BMP (0.0-1.0). For example, 0.2 removes 20% of particulate P. The value is applied as (1 - ptlp_eff) to reduce the particulate P load.
