---
description: Pointer to the wetland hydrology file
---

# hyd

The pointer to the wetland hydrology file is a foreign key referencing [name](../hydrology.wet/name.md) in [**hydrology.wet**](../hydrology.wet/).

The literal value `paddy` also activates special paddy behavior. SWAT+ retains the paddy water-surface-area setup and routes outflow through the paddy weir-release routine instead of the ordinary wetland decision-table and reservoir-hydrology path.
