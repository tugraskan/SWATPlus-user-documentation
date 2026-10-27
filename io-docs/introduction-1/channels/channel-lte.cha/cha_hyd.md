---
description: Pointer to the channel hydrology and sediment file
---

# cha\_hyd

The pointer to the channel hydrology and sediment file is a foreign key referencing [name](../hyd-sed-lte.cha/name.md) in [**hyd-sed-lte.cha**](../hyd-sed-lte.cha/).

SWAT+ main (6f515368) also matches this same name against records in sed_nut.cha to select the channel's additional sediment and nutrient parameters.
