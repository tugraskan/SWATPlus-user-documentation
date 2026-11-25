---
description: Channel (stream) order
---

# order

**Code reference:** `sd_chd(idb)%order` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_module.f90#L20)).

Order of the channel in the stream network. SWAT+ copies it to each channel at the start of the simulation and uses it in the channel sediment routine. Decision tables can test the channel order in conditions and change it with actions.
