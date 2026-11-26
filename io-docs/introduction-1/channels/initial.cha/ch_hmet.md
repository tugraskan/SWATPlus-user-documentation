---
description: Intended heavy-metal initialization pointer (read but not used in initial.cha in main 6f515368)
---

# hmet

**Code reference:** `ch_init(ich)%hmet` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/channel_data_module.f90#L44)).

Intended pointer to the channel heavy-metal initialization record (`character(len=16)`).

*(Note: In SWAT+ main (6f515368) and dev (aa4179fe), this column is parsed into memory but is not used in simulation calculations).* The heavy-metal lookup block in [`sd_channel_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_read.f90#L251-L257) is commented out.
