---
description: Harvest index for optimal growth conditions
---

# harv\_idx

**Code reference:** `pldb(ic)%hvsti` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_data_module.f90#L39)).

{% hint style="warning" %}
SWAT+ main (`6f515368`) replaces any `harv_idx` greater than 0.7 with **0.02** ([`plantparm_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plantparm_init.f90#L37-L38)). The source comment says this is meant for trees and grasses, but it applies to every plant, and the table default of 0.76 is above the cutoff. This comes from source reading, not a model run.
{% endhint %}

The value is the ceiling for the daily seed (yield) fraction ([`pl_seed_gro.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_seed_gro.f90#L31-L45)).

The harvest index defines the fraction of the aboveground biomass that is removed in a harvest operation. This value defines the fraction of plant biomass that is “lost” from the system and unavailable for conversion to residue and subsequent decomposition. For crops where the harvested portion of the plant is aboveground, the harvest index is always a fraction less than 1. For crops where the harvested portion is belowground, the harvest index may be greater than 1. Two harvest indices are provided in the database, the harvest index for optimal growing conditions and the harvest index under highly stressed growing conditions ([harv\_idx\_ws](harv_idx_ws.md)).

To determine the harvest index, the plant biomass removed during the harvest operation is dried at least 2 days at 65°C and weighed. The total aboveground plant biomass in the field should also be dried and weighed. The harvest index is then calculated by dividing the weight of the harvested portion of the plant biomass by the weight of the total aboveground plant biomass. Plants will need to be grown in two different plots where optimal climatic conditions and stressed conditions are produced to obtain values for both harvest indices.
