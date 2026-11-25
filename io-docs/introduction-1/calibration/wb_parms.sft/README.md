---
description: Parameter change bounds for HRU, HRU-LTE, and land-sediment soft calibration.
---

# wb\_parms.sft

Specifies the step-change limits and absolute parameter bounds used during water-balance and land-sediment soft calibration, read into `ls_prms` (`soft_calib_parms`, [`calibration_data_module.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calibration_data_module.f90#L71-L79)) by [`ls_read_parms_cal.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ls_read_parms_cal.f90#L23-L43).

## Number of parameters

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [mlsp](mlsp.md) | Number of landscape soft-calibration parameter rows | integer | — | — | > 0 |

## Parameter bounds

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [name](name.md) | Parameter label (parsed but unused; rows are indexed positionally) | string | — | — | — |
| [chg\_typ](chg_typ.md) | Change type label (parsed but unused) | string | — | — | — |
| [neg](neg.md) | Lower limit on cumulative or per-step adjustment | real | — | 0 | — |
| [pos](pos.md) | Upper limit on cumulative or per-step adjustment | real | — | 0 | — |
| [lo](lo.md) | Absolute lower bound clamped on the model parameter | real | — | 0 | — |
| [up](up.md) | Absolute upper bound clamped on the model parameter | real | — | 0 | — |

SWAT+ ignores `name` and `chg_typ` and indexes `ls_prms(1)` through `ls_prms(10)` strictly by row order:

1. `cn2`: HRU-LTE curve number in [`caltsoft_hyd.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/caltsoft_hyd.f90#L68-L165) (also referenced by [`calsoft_sed.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_sed.f90#L65) for `tconc` pass-1 upper-change check and [`caltsoft_hyd.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/caltsoft_hyd.f90#L707-L714) for pass-2 `cn3_swf` change limits).
2. `esco`: HRU soil evaporation compensation factor in [`calsoft_hyd.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_hyd.f90#L68-L161) and [`calsoft_hyd_bfr_et.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_hyd_bfr_et.f90#L61-L154).
3. `latq_co`: HRU lateral flow coefficient in [`calsoft_hyd.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_hyd.f90#L429-L511) and [`calsoft_hyd_bfr_latq.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_hyd_bfr_latq.f90#L65-L148).
4. `pet_co`: HRU PET adjustment factor in [`calsoft_hyd.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_hyd.f90#L223-L241) and [`calsoft_hyd_bfr_pet.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_hyd_bfr_pet.f90#L59-L76), temporarily halved on pass 1 of [`calsoft_hyd_bfr.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_hyd_bfr.f90#L33-L45).
5. `slope`: HRU slope adjustment in [`calsoft_sed.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_sed.f90#L148-L189).
6. `tconc`: HRU time-of-concentration adjustment in [`calsoft_sed.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_sed.f90#L66-L109).
7. `etco`: HRU-LTE ET coefficient in [`caltsoft_hyd.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/caltsoft_hyd.f90#L223-L308).
8. `perco`: HRU and HRU-LTE percolation coefficient in [`calsoft_hyd.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_hyd.f90#L558-L661), [`calsoft_hyd_bfr_perc.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_hyd_bfr_perc.f90#L62-L165), and [`caltsoft_hyd.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/caltsoft_hyd.f90#L354-L444).
9. `revapc`: HRU-LTE revap coefficient in [`caltsoft_hyd.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/caltsoft_hyd.f90#L496-L582).
10. `cn3_swf`: HRU and HRU-LTE soil-water factor in [`calsoft_hyd.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_hyd.f90#L285-L815), [`calsoft_hyd_bfr_surq.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_hyd_bfr_surq.f90#L60-L149), and [`caltsoft_hyd.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/caltsoft_hyd.f90#L628-L726).
