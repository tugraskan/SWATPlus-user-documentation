---
description: Intended salt-initialization pointer (read but not used in initial.cha in main 6f515368)
---

# salt

**Code reference:** `ch_init(ich)%salt` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/channel_data_module.f90#L45)).

Intended salt-initialization pointer. SWAT+ main (6f515368) reads this `initial.cha` field but does not use its value afterward. Active channel salt initialization uses the salt pointer in `initial.cha_cs` ([`sd_channel_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_read.f90#L258-L264)).
