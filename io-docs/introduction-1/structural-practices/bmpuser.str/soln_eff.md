---
description: Soluble N removal by BMP
---

# soln\_eff

**Code reference:** `bmpuser_db(ibmpop)%bmp_sn`

**Declared type:** `bmpuser_operation` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/scen_read_bmpuser.f90#L43), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/mgt_operations_module.f90#L66)).

Enter the fraction of soluble nitrogen removed by this BMP (0.0-1.0). For example, 0.2 removes 20% of soluble N. The value is applied as (1 - soln_eff) to reduce the soluble N load.
