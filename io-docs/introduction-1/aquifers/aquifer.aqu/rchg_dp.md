---
description: Recharge to deeper aquifers
---

# rchg\_dp

**Code reference:** `aqudb(i)%seep`

**Declared type:** `aquifer_database` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/aqu_read.f90#L55), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/aquifer_module.f90#L18)).

This parameter defines the fraction of root zone percolation reaching a deeper aquifer. If a deeper aquifer is defined in **aquifer.aqu** and [**aquifer.con**](../../connectivity/hru.con/), its groundwater flow can be routed to any other spatial object using [**aquifer.con**](../../connectivity/hru.con/). If no deeper aquifer is defined or if the receiving deeper aquifer is not connected to another spatial object, the water that recharges the deeper aquifer is assumed to be lost from the watershed.
