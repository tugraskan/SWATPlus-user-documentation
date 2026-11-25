---
description: Channel sediment pointer placeholder (parsed into memory but unused)
---

# cha\_sed

**Code reference:** `sd_dat(i)%sedc` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_module.f90#L135)).

16-character placeholder string read from `channel-lte.cha` in [`sd_channel_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_read.f90#L222).

*(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations).* Additional channel sediment and nutrient parameters in `sed_nut.cha` are matched using [`cha_hyd`](cha_hyd.md) ([`sd_channel_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_read.f90#L284-L289)).
