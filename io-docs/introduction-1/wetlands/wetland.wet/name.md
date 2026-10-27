---
description: Name of the wetland
---

# name (wetland.wet)

**Code reference:** `wet_dat_c(ires)%name`

**Declared type:** `reservoir_data_char_input` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/wet_read.f90#L66), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/reservoir_data_module.f90#L6)).

The name of the wetland is a primary key referenced by [surf\_stor](../../hydrologic-response-units/hru-data.hru/surf_stor.md) in [**hru-data.hru**](../../hydrologic-response-units/hru-data.hru/). All names in the **wetland.wet** file must be unique.
