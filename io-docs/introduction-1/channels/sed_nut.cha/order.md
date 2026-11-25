---
description: "Order label stored with this channel parameter record"
---

# order

**Code reference:** `sd_chd1(idb)%order` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_module.f90#L47)).

Character order label stored with this channel parameter record (`character(len=16)`).

*(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations).* It is not copied to `sd_ch` during initialization in [`sd_hydsed_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_hydsed_init.f90#L106-L116).
