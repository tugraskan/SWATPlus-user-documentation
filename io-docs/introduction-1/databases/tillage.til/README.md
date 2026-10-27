---
description: >-
  The tillage database summarizes parameters used by the model to simulate the
  effects of different types of tillage equipment.
---

# tillage.til

| Field                  | Description                                     |  Type  |   Unit   | Default |   Range   |
| ---------------------- | ----------------------------------------------- | :----: | :------: | :-----: | :-------: |
| [name](name_tilldb.md)\* | Name of the tillage record                      | string |    n/a   |   n/a   |    n/a    |
| [mix\_eff](mix_eff.md)\* | Mixing efficiency of the tillage operation      |  real  | fraction |   0.0   |  0.0-1.0  |
| [mix\_dp](mix_dp.md)\* | Depth of mixing caused by the tillage operation |  real  |    mm    |   0.0   | 0.0-750.0 |
| rough\* | Currently not used | real | mm |  |  |
| ridge\_ht | Currently not used | real | mm |  |  |
| ridge\_sp | Currently not used | real | mm |  |  |

\* Input-file labels marked with an asterisk have different Fortran names: `name` → `tilldb(itl)%tillnm`; `mix_eff` → `tilldb(itl)%effmix`; `mix_dp` → `tilldb(itl)%deptil`; `rough` → `tilldb(itl)%ranrns`. [Reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/till_parm_read.f90#L47).
