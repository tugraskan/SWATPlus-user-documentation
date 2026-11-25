---
description: "Soil layer group (1 = top 10 mm layer, 2 = deeper layers) of a carbon_lyr.bsn row"
---

# layer\_id

**Code reference:** `layer_id` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_bsn_read.f90#L36), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_bsn_read.f90#L132)).

Row key of `carbon_lyr.bsn`. Row `1` applies to soil layer 1, the 10 mm surface layer, and row `2` to all deeper layers ([`cbn_zhang2.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cbn_zhang2.f90#L317-L324)). Enter one row for each of `1` and `2`.

[`carbon_bsn_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_bsn_read.f90#L138-L142) skips rows with any other value and writes a warning to `diagnostics.out`. The run stops if fewer than two rows are accepted ([`carbon_bsn_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_bsn_read.f90#L160-L167)). The check counts rows, not distinct values, so two rows with the same value pass and leave the other layer group's coefficients at 0. This is listed in `MODEL_ISSUES.md`.

The SWAT+ example file (`refdata/Ames_sub1`) heads this column `layer` and uses 1 and 2.
