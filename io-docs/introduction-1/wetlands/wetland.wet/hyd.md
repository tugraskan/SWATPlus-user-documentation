---
description: Pointer to the wetland hydrology file
---

# hyd

**Code reference:** `wet_dat_c(ires)%hyd` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/reservoir_data_module.f90#L8)).

The pointer to the wetland hydrology file is a foreign key referencing [name](../hydrology.wet/name.md) in [**hydrology.wet**](../hydrology.wet/).

The literal value `paddy` also activates special paddy behavior. SWAT+ retains the paddy water-surface-area setup and routes outflow through the paddy weir-release routine instead of the ordinary wetland decision-table and reservoir-hydrology path.
