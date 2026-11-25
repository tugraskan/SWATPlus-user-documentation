---
description: Intended pathogen-initialization pointer (read but not used in initial.cha in main 6f515368)
---

# path

**Code reference:** `ch_init(ich)%path` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/channel_data_module.f90#L43)).

Intended pointer to the channel pathogen initialization record (`character(len=16)`).

*(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations).* Active channel pathogen initialization matches `ch_init_cs%path` from `initial.cha_cs` against `path_water.ini` in [`sd_channel_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_read.f90#L245-L250).
