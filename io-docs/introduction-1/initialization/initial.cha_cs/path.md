---
description: "Name of the referenced pathogen initialization record"
---

# path

**Code reference:** `ch_init_cs(ich)%path` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/channel_data_module.f90#L53)).

Foreign key referencing [path\_init\_name(ipathi)](../path_water.ini/path_init_name_ipathi.md) in [**path\_water.ini**](../path_water.ini/), matched in [`sd_channel_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_read.f90#L246) and applied to `ch_water%path` and `ch_benthic%path` in [`sd_hydsed_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_hydsed_init.f90#L279-L280). (Note that `ch_water%path` and `ch_benthic%path` are not subsequently read in simulation calculations in SWAT+ main `6f515368`).
