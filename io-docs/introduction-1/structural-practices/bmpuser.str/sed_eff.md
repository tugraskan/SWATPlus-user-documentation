---
description: Sediment removal by BMP
---

# sed\_eff

**Code reference:** `bmpuser_db(ibmpop)%bmp_sed` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/mgt_operations_module.f90#L62)).

Enter the fraction of sediment load removed by this BMP (0.0-1.0). For example, 0.2 removes 20% of sediment. The value is applied as (1 - sed_eff) to reduce the sediment load.
