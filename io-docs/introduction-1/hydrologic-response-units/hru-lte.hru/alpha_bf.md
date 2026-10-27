---
description: Baseflow alpha factor
---

# alpha\_bf

**Code reference:** `hlt_db(i)%abf`

**Declared type:** `swatdeg_hru_data` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/hru_lte_read.f90#L117), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/hru_lte_module.f90#L22)).

The input is a daily groundwater recession constant. SWAT+ converts it to a daily retention factor with exp(-alpha_bf) before calculating shallow-aquifer flow.
