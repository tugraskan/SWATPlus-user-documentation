---
description: Pointer to the reservoir hydrology file
---

# hyd

**Code reference:** `res_dat_c(ires)%hyd`

**Declared type:** `reservoir_data_char_input` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/res_read.f90#L74), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/reservoir_data_module.f90#L8)).

The pointer to the reservoir hydrology file is a foreign key referencing [name](../hydrology.res/name.md) in [**hydrology.res**](../hydrology.res/).
