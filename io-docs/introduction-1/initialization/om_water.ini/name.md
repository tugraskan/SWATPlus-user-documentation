---
description: Name of water and nutrient initialization
---

# name (om\_water.ini)

**Code reference:** `om_init_name(ichi)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L91)).

Name of the organic-mineral water initialization record, read in [`om_water_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/om_water_init.f90#L54). It is matched against the `org_min` field in [**initial.res**](../../reservoirs/initial.res/) for reservoirs ([`res_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_read.f90#L86)) and wetlands ([`wet_initial.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_initial.f90#L54)), and in [**initial.cha**](../../channels/initial.cha/) for SWAT-DEG channels ([`sd_channel_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_read.f90#L232)).
