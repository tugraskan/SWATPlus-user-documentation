---
description: >-
  Start of growing season for non-tropical/start of monsoon initialization
  period for tropical
---

# grow\_start

**Code reference:** `hlt_db(i)%igrow1`

**Declared type:** `swatdeg_hru_data` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/hru_lte_read.f90#L117), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/hru_lte_module.f90#L37)).

Name of a decision-table entry in lum.dtl. For non-tropical HRUs, it represents the start of the growing season (pl_grow_sum). For tropical HRUs, it represents the start of the monsoon initialization period. SWAT+ writes a warning if the name is not found in lum.dtl.
