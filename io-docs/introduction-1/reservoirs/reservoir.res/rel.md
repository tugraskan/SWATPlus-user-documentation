---
description: Name of the reservoir release decision table or control table
---

# rel

**Code reference:** `res_dat_c(ires)%release`

**Declared type:** `reservoir_data_char_input` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/res_read.f90#L74), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/reservoir_data_module.f90#L9)).

Enter the name of a reservoir release decision table in [**res_rel.dtl**](../../decision-tables/lum.dtl/). To use a reservoir control table from **res_conds.dat**, enter its name beginning with `ctbl_`.
