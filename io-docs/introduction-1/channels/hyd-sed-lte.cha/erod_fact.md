---
description: Bank erosion exponent (currently not used)
---

# erod\_fact

**Code reference:** `sd_chd(idb)%w_yr` on SWAT+ dev, `bank_exp` on main ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_module.f90#L27)).

On SWAT+ dev this column is read into `w_yr`, the average number of channel widths eroded per year. The bank-erosion routine overwrites it with `0.02` on every call before using it, so the entered value has no effect ([`sd_channel_sediment3.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_sediment3.f90#L209-L238)). (On SWAT+ main it was read as a bank-erosion exponent in an equation that was commented out.)
