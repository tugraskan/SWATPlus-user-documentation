---
description: This file contains pre-defined burning/fire operations.
---

# fire.ops

| Field                      | Description                         | Type    | Unit      | Default | Range      |
| -------------------------- | ----------------------------------- | ------- | --------- | ------- | ---------- |
| [name](name_fire.md)       | ​Fire operation name                | ​string | n/a       | n/a     | n/a        |
| [chg\_cn2](chg_cn2.md)\* | Change in SCS Curve Number II value | real    | ​n/a      | ​0.0    | ​n/a       |
| [frac\_burn](frac_burn.md)\* | ​Fraction burned | real | ​fraction | ​0.0 | 0.0-1.0 |

\* Input-file labels marked with an asterisk have different Fortran names: `chg_cn2` → `fire_db(ifireop)%cn2_upd`; `frac_burn` → `fire_db(ifireop)%fr_burn`. [Reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/mgt_read_fireops.f90#L45).
