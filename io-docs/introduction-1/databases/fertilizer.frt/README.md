---
description: >-
  The fertilizer database summarizes parameters used by the model to simulate
  different types of fertilizer and manure.
---

# fertilizer.frt

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [name](name_fertdb.md) | Name of the fertilizer record | string | n/a | n/a | n/a |
| [min\_n](min_n.md) | Fraction of fertilizer that is mineral N (NO3+NH3) | real | fraction | 1.0 | 0.0-1.0 |
| [min\_p](min_p.md) | Fraction of fertilizer that is mineral P | real | fraction | 0.0 | 0.0-1.0 |
| [org\_n](org_n.md) | Fraction of fertilizer that is organic N | real | fraction | 0.0 | 0.0-1.0 |
| [org\_p](org_p.md) | Fraction of fertilizer that is organic P | real | fraction | 0.0 | 0.0-1.0 |
| [nh3\_n](nh3_n.md) | Fraction of mineral N content of fertilizer that is NH3 | real | fraction | 0.0 | 0.0-1.0 |

The file has a title line and a column-header line. Only the six columns above are read; anything after them on a line, such as a pathogen or description column, is not read ([`fert_parm_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/fert_parm_read.f90#L47)). The row order also matters when [salt\_fertilizer.frt](../salt_fertilizer.frt/) or [fertilizer.frt\_cs](../fertilizer.frt_cs/) is used.
