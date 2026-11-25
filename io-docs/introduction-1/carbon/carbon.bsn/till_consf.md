---
description: "Daily rate at which the tillage effect on decomposition fades as soil settles"
---

# till\_consf

**Code reference:** `till_consf` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/tillage_data_module.f90#L17), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_bsn_read.f90#L75), [calibration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_parm_select.f90#L489-L490)).

Tillage consolidation factor. Each day after tillage, [`mgt_tillfactor.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_tillfactor.f90#L97-L108) reduces each layer's tillage mixing factor as the soil settles, and sets it to 0 once it falls to 0.01:

$$
F_{till} = (1 - k) \, F_{till}, \qquad k = k_{till} \min\left(1, \frac{SW}{FC}\right)
$$

where:

- $F_{till}$ is the layer's tillage mixing factor (dimensionless),
- $k$ is the daily decay fraction (1/day),
- $k_{till}$ is `till_consf` (fraction/day),
- $SW$ is the layer's soil water content (mm), and
- $FC$ is the layer's field capacity (mm).

The tillage factor changes decomposition only when [idc\_till](../../basin-1/codes.bsn/idc_till.md) `= 3` ([`cbn_zhang2.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cbn_zhang2.f90#L395-L398)).

The SWAT+ example file (`refdata/Ames_sub1`) heads this column `till_consol` and uses 0.10. The calibration parameter is `till_consol`.
