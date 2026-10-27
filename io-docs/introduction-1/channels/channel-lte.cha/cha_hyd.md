---
description: Pointer to the channel hydrology and sediment file
---

# cha\_hyd

**Code reference:** `sd_dat(i)%hydc`

**Declared type:** `swatdeg_datafiles` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/sd_channel_read.f90#L222), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/sd_channel_module.f90#L137)).


The pointer to the channel hydrology and sediment file is a foreign key referencing [name](../hyd-sed-lte.cha/name.md) in [**hyd-sed-lte.cha**](../hyd-sed-lte.cha/).

SWAT+ main (6f515368) also matches this same name against records in sed_nut.cha to select the channel's additional sediment and nutrient parameters.
