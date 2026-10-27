---
description: This file contains pre-defined street sweeping operations.
---

# sweep.ops

| Field                      | Description                                   | Type   | Unit     | Default | Range   |
| -------------------------- | --------------------------------------------- | ------ | -------- | ------- | ------- |
| [name](name_sweep.md)      | Street sweeping operation name                | string | n/a      | n/a     | n/a     |
| [swp\_eff](swp_eff.md)\* | Removal efficiency of sweeping operation      | real   | fraction | 0.0     | 0.0-1.0 |
| [frac\_curb](frac_curb.md)\* | Fraction of the curb length that is sweepable | real   | fraction | 0.0     | 0.0-1.0 |

\* Input-file labels marked with an asterisk have different Fortran names: `swp_eff` → `sweepop_db(isweepop)%eff`; `frac_curb` → `sweepop_db(isweepop)%fr_curb`. [Reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/mgt_read_sweepops.f90#L47).
