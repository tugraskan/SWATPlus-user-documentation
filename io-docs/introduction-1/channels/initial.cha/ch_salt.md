---
description: Currently not used in initial.cha in SWAT+ main (6f515368)
---

# salt

**Code reference:** `ch_init(ich)%salt`

**Declared type:** `channel_init_datafiles` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/ch_read_init.f90#L49), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/channel_data_module.f90#L45)).

SWAT+ main (6f515368) reads the salt field as part of each initial.cha record but does not use its value afterward. Channel salt initialization instead uses the salt pointer read from initial.cha_cs.
