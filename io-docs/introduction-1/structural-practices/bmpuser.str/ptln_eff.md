---
description: Particulate N removal by BMP
---

# ptln\_eff

**Code reference:** `bmpuser_db(ibmpop)%bmp_pn` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/mgt_operations_module.f90#L65)).

Enter the fraction of particulate nitrogen removed by this BMP (0.0-1.0). For example, 0.2 removes 20% of particulate N. The value is applied as (1 - ptln_eff) to reduce the particulate N load.
