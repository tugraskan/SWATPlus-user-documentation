---
description: Pointer to the channel hydrology and sediment file
---

# cha\_hyd

**Code reference:** `sd_dat(i)%hydc` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_module.f90#L134)).

The pointer to the channel hydrology and sediment file is a foreign key referencing [name](../hyd-sed-lte.cha/name.md) in [**hyd-sed-lte.cha**](../hyd-sed-lte.cha/).

SWAT+ main (6f515368) also matches this same name against records in sed_nut.cha to select the channel's additional sediment and nutrient parameters.
