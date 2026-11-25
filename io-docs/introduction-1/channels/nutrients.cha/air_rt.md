---
description: Reaeration rate in accordance with Fickian diffusion in the channel at 20ºC
---

# air\_rt

**Code reference:** `ch_nut(ich)%rk2` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/channel_data_module.f90#L123)).

Enter this field in `1/day` (table default `50.0`, range `0.0–100.0`). In [`ch_read_nut.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_nut.f90#L100), values `<= 0.` are replaced with `1.0`, and [`ch_read_nut.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_nut.f90#L117) divides `rk2` by the number of routing time steps per day (`time%step`) before use in [`ch_watqual4.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_watqual4.f90#L269-L270).
