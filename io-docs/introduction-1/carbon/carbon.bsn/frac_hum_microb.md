---
description: "Share of the sequestered carbon placed in the microbial pool at the start"
---

# frac\_hum\_microb

**Code reference:** `org_frac%frac_hum_microb` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_module.f90#L129), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_bsn_read.f90#L71), [calibration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_parm_select.f90#L475-L476)).

Share of the non-litter carbon ((1 − [frac\_litter](frac_litter.md)) × layer organic carbon) that [`soil_nutcarb_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_nutcarb_init.f90#L162-L166) places in the microbial pool. Microbial nitrogen and phosphorus are then set from fixed C:N = 8 and C:P = 80 ratios.

The three shares `frac_hum_microb`, [frac\_hum\_slow](frac_hum_slow.md) and [frac\_hum\_passive](frac_hum_passive.md) should add up to 1; the reader does not check this.

The SWAT+ example file (`refdata/Ames_sub1`) heads this column `init_microb` and uses 0.02. The calibration parameter is `init_microb`.
