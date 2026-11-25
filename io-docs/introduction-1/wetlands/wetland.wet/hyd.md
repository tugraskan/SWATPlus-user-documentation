---
description: Pointer to the wetland hydrology file
---

# hyd

**Code reference:** `wet_dat_c(ires)%hyd` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_data_module.f90#L8)).

The pointer to the wetland hydrology file is a foreign key referencing [name](../hydrology.wet/name.md) in [**hydrology.wet**](../hydrology.wet/).

The literal value `paddy` activates special rice-paddy behavior. SWAT+ routes outflow through the paddy weir-release routine instead of the standard wetland decision-table release, and maintains flat ponding across 100% of the HRU area, bypassing the dynamic depth-area curve.
