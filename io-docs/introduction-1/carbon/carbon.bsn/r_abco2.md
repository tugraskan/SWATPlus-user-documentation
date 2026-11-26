---
description: "Fraction of transformed microbial carbon respired as CO2 (soil layer 1)"
---

# r\_abco2

**Code reference:** `org_allo(layer_id)%abco2` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_module.f90#L96), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_bsn_read.f90#L155), [calibration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_parm_select.f90#L532-L533)).

Fraction of the transformed microbial carbon released as CO2 ([`cbn_zhang2.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cbn_zhang2.f90#L774)). Row `1` applies to soil layer 1, the 10 mm surface layer, and row `2` to all deeper layers ([`cbn_zhang2.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cbn_zhang2.f90#L317-L324)). For the deeper layers, [`cbn_zhang2.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cbn_zhang2.f90#L478-L480) replaces it with $0.17 + 0.0068 \cdot \text{sand}$ (sand in %) before it is used, so the row `2` value has no effect.

The SWAT+ example file (`refdata/Ames_sub1`) heads this column `abco2` and uses 0.55 and 0.0 for rows 1 and 2. The calibration parameter is `abco2` (by layer).
