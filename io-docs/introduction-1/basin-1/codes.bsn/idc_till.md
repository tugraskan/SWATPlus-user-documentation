---
description: Tillage method used when carbon = 2
---

# idc\_till

**Code reference:** `bsn_cc%idc_till` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/basin_module.f90#L71)).

Selects the tillage method used by the carbon routine. It is used only when carbon is set to 2.

| Value | Tillage method     |
| ----- | ------------------ |
| 1     | DSSAT              |
| 2     | EPIC               |
| 3     | Kemanian (default) |
| 4     | DNDC               |
