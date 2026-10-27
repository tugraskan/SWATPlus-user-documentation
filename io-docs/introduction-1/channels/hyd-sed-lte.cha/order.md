---
description: Channel (stream) order
---

# order

**Code reference:** `sd_chd(idb)%order` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/sd_channel_module.f90#L20)).

Order of the channel in the stream network. SWAT+ copies it to each channel at the start of the simulation and uses it in the channel sediment routine. Decision tables can test the channel order in conditions and change it with actions.
