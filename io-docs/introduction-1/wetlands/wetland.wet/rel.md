---
description: Pointer to the reservoir and wetland release decision table file
---

# rel

**Code reference:** `wet_dat_c(ires)%release`

**Declared type:** `reservoir_data_char_input` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/wet_read.f90#L66), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/reservoir_data_module.f90#L9)).

The pointer to the wetland release file is a foreign key referencing a decision table name in [**res\_rel.dtl**](../../decision-tables/lum.dtl/).
