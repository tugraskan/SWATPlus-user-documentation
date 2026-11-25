---
description: "Median (D50) particle size diameter of the channel bed sediment"
---

# bed_d50

**Code reference:** `ch_sed(ich)%bed_d50` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/channel_data_module.f90#L101)).

Median (`D50`) particle size diameter of the channel bed sediment (`um`). [`ch_read_sed.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_sed.f90#L82-L83) replaces values `<= 1.0e-6` with `500.` and caps values above `10000.` at `10000.`. [`ch_initial.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_initial.f90#L52-L82) converts `bed_d50` from micrometers to millimeters (`bed_d50 / 1000.`) to assign bed clay, silt, sand, and gravel fractions.
