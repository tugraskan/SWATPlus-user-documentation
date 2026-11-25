---
description: "Channel (reach) identifier for the shading entry"
---

# cha

**Code reference:** `shf_db(idlsu)%cha` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L1200)).

This integer identifies the specific channel reach (`ich`). It is matched alongside `jday` in [`ch_temp.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_temp.f90#L376) (read by [`shade_factor_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/shade_factor_read.f90#L50)). Because `w_temp(0)%sf_on` remains `0`, source reading indicates this lookup is not reached at `6f515368`.
