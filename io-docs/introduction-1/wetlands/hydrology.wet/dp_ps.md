---
description: Average depth of water at principal spillway
---

# dp\_ps

**Code reference:** `wet_hyddb(ires)%pdep` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/reservoir_data_module.f90#L85)).

The average depth of water at principal spillway is used to calculate the principal volume of the wetland and to set the default weir height (if the weir height is specified in column [height](../../reservoirs/weir.res/vel_co.md) in [**weir.res**](../../reservoirs/weir.res/), this value will override the default weir height calculated based on dp\_ps). &#x20;

The principal volume of the wetland is used during daily wetland simulation in the equation that updates surface area as storage changes and for wetland release conditions and actions.
