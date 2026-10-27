---
description: End of growing season for non-tropical/end of monsoon initialization period for tropical
---

# grow\_end

**Code reference:** `hlt_db(i)%igrow2` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/hru_lte_module.f90#L39)).

Name of a decision-table entry in lum.dtl. For non-tropical HRUs, it represents the end of the growing season (pl_end_sum). For tropical HRUs, it represents the end of the monsoon initialization period. SWAT+ writes a warning if the name is not found in lum.dtl.
