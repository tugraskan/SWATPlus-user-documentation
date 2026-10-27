---
description: Harvest efficiency
---

# harv\_eff

**Code reference:** `harvop_db(iharvop)%eff` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/mgt_operations_module.f90#L114)).

Harvest efficiency is the fraction of harvested material exported from the HRU; material not exported remains in or is transferred to plant-residue or soil pools according to the harvest routine. A value of 0.0 exports no harvested yield, while 1.0 exports the full calculated yield. For residue harvest, a separately scheduled efficiency near zero causes SWAT+ to use the harv_eff value from harv.ops instead.
