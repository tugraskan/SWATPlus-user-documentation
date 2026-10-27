---
description: Harvest index target specified at harvest
---

# harv\_idx

**Code reference:** `harvop_db(iharvop)%hi_ovr`

**Declared type:** `harvest_operation` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/mgt_read_harvops.f90#L44), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/mgt_operations_module.f90#L113)).

This variable will force the ratio of yield to total above-ground biomass to the specified value. If biomass is cut and removed (e.g., in hay cuttings), _harv\_idx_ must be used to specify the amount of biomass cut. For grain harvest, the harvest index in the plant growth database ([**plants.plt**](../../databases/plants.plt/)) is used instead of _harv\_idx_, which assumes that only the seed is being harvested.&#x20;
