---
description: >-
  This file lists the USLE P values and slope lengths for various conservation
  practices.
---

# cons\_practice.lum

| Field                           | Description                        | Type   | Unit | Default | Range   |
| ------------------------------- | ---------------------------------- | ------ | ---- | ------- | ------- |
| [name](name_consp.md)           | Name of the conservation practice  | string | ​n/a | n/a     | n/a     |
| [usle\_p](usle_p.md)\* | USLE P factor                      | ​real  | none | 1.0     | 0.0-1.0 |
| [slp\_len\_max](slp_len_max.md)\* | Maximum slope length               | real   | m    | 1.0     |         |

\* Input-file labels marked with an asterisk have different Fortran names: `usle_p` → `cons_prac(icp)%pfac`; `slp_len_max` → `cons_prac(icp)%sl_len_mx`. [Reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/cons_prac_read.f90#L45).
