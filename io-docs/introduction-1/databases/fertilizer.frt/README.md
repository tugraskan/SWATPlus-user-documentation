---
description: >-
  The fertilizer database summarizes parameters used by the model to simulate
  different types of fertilizer and manure.
---

# fertilizer.frt

| Field                  | Description                                             |  Type  |   Unit   | Default |  Range  |
| ---------------------- | ------------------------------------------------------- | :----: | :------: | :-----: | :-----: |
| [name](name_fertdb.md)\* | Name of the fertilizer record                           | string |    n/a   |   n/a   |   n/a   |
| [min\_n](min_n.md)\* | Fraction of fertilizer that is mineral N (NO3+NH3)      |  real  | fraction |   1.0   | 0.0-1.0 |
| [min\_p](min_p.md)\* | Fraction of fertilizer that is mineral P                |  real  | fraction |   0.0   | 0.0-1.0 |
| [org\_n](org_n.md)\* | Fraction of fertilizer that is organic N                |  real  | fraction |   0.0   | 0.0-1.0 |
| [org\_p](org_p.md)\* | Fraction of fertilizer that is organic P                |  real  | fraction |   0.0   | 0.0-1.0 |
| [nh3\_n](nh3_n.md)\* | Fraction of mineral N content of fertilizer that is NH3 |  real  | fraction |   0.0   | 0.0-1.0 |

\* Input-file labels marked with an asterisk have different Fortran names: `name` → `fertdb(it)%fertnm`; `min_n` → `fertdb(it)%fminn`; `min_p` → `fertdb(it)%fminp`; `org_n` → `fertdb(it)%forgn`; `org_p` → `fertdb(it)%forgp`; `nh3_n` → `fertdb(it)%fnh3n`. [Reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/fert_parm_read.f90#L47).
