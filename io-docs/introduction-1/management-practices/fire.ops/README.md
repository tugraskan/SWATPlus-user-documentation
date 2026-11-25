---
description: This file contains pre-defined burning/fire operations.
---

# fire.ops

This file defines pre-defined burning/fire operations read by [`mgt_read_fireops.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_read_fireops.f90#L25-L54) and executed in [`pl_burnop.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/pl_burnop.f90#L1-L80).

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [name](name_fire.md) | Fire operation name | string | n/a | n/a | n/a |
| [chg\_cn2](chg_cn2.md) | Change in SCS Curve Number II value | real | n/a | 0.0 | n/a |
| [frac\_burn](frac_burn.md) | Fraction burned | real | fraction | 0.0 | 0.0-1.0 |
