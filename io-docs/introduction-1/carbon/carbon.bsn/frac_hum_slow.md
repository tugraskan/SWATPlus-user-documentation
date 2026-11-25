---
description: "Share of the sequestered carbon placed in the slow humus pool at the start"
---

# frac\_hum\_slow

**Code reference:** `org_frac%frac_hum_slow` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_module.f90#L130), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_bsn_read.f90#L72), [calibration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_parm_select.f90#L477-L478)).

Share of the non-litter carbon ((1 − [frac\_litter](frac_litter.md)) × layer organic carbon) that [`soil_nutcarb_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_nutcarb_init.f90#L175-L179) places in the slow humus pool, with C:N = 10 and C:P = 80.

It is used only when [mathers\_int](mathers_int.md) is not `1`. With `mathers_int = 1` the slow pool takes whatever the passive, microbial and litter pools leave, and this column has no effect.

The SWAT+ example file (`refdata/Ames_sub1`) heads this column `init_slow` and uses 0.44. The calibration parameter is `init_slow`.
