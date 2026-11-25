---
description: Tillage method used when carbon = 2
---

# idc\_till

**Code reference:** `bsn_cc%idc_till` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L71), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_cc.f90#L24)).

Selects the tillage mixing formulation in [`cbn_zhang2.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cbn_zhang2.f90#L374). It is evaluated only when [carbon](carbon.md) = `2` (struct default `3`).

| Value | Tillage method |
| ----- | -------------- |
| 1 | DSSAT |
| 2 | EPIC |
| 3 | Kemanian (default) |
| 4 | DNDC |
