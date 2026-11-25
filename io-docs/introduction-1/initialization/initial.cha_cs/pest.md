---
description: "Name of the referenced pesticide initialization record (read but not used in main 6f515368)"
---

# pest

**Code reference:** `ch_init_cs(ich)%pest` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/channel_data_module.f90#L52)).

Intended pointer to a pesticide initialization record, read in [`ch_read_init_cs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_init_cs.f90#L48) and never subsequently read. Channel pesticide initialization uses [pest](../../channels/initial.cha/ch_pest.md) (`ch_init%pest`) in [**initial.cha**](../../channels/initial.cha/) ([`sd_channel_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_read.f90#L239)).

*(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations).*
