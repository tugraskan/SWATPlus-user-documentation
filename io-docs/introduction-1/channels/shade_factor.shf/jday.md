---
description: "Day of year"
---

# jday

**Code reference:** `shf_db(idlsu)%jday` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L1199)).

Day-of-year value matched together with the channel number in [`ch_temp.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_temp.f90#L371-L381) (read by [`shade_factor_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/shade_factor_read.f90#L50)). In the file-based shading branch, day `366` sets `ssff = 0.5` rather than performing a row lookup. Because `w_temp(0)%sf_on` remains `0`, source reading indicates this branch is not reached at `6f515368`.
