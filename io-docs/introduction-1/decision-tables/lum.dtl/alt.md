---
description: Alternative
---

# alt

**Code reference:** `dtbl_lum(i)%alt(ic,ial)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditional_module.f90#L34)).

Enter one comparison per alternative. Numeric conditions recognize `<`, `>`, `<=`, `>=`, `=`, and `/=` (not equal). A hyphen skips the numeric comparison. Write the inequality token as `'/='` in the input file so its leading slash is read as data. [`cond_real.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cond_real.f90#L19-L52) · [`cond_integer.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cond_integer.f90#L15-L48)

Category conditions work differently. `plant_gro`, `plant_name_gro`, `hyd_soil_group`, `land_use`, `cal_group`, and `ch_order` filter only on `=`; any other token, including `'/='`, lets the alternative pass. `plant_com` and `tile_drained` use `=` for yes and `'/'` for no. `tillage` fails the alternative for every token other than a matching `=`, so a hyphen does not skip it. The probability conditions filter on `=`, except `prob`, which is numeric. [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L190-L222) · [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L461-L476) · [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L648-L730)
