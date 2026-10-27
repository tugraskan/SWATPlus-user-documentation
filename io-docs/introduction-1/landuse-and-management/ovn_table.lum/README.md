---
description: >-
  This file lists overland Manning's n values for different tillage and land
  cover types.
---

# ovn\_table.lum

| Field                    | Description                             |  Type  | Unit | Default | Range |
| ------------------------ | --------------------------------------- | :----: | :--: | :-----: | :---: |
| [name](name_ovn.md) | Overland flow Manning's n class name | string | n/a | n/a | n/a |
| [ovn\_mean](ovn_mean.md)\* | Mean overland flow Manning’s n value    |  real  |  n/a |   0.5   |       |
| [ovn\_min](ovn_min.md)   | Minimum overland flow Manning’s n value |  real  |  n/a |   0.5   |       |
| [ovn\_max](ovn_max.md)   | Maximum overland flow Manning’s n value |  real  |  n/a |   0.5   |       |

\* Input-file labels marked with an asterisk have different Fortran names: `ovn_mean` → `overland_n(il)%ovn`. [Reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/overland_n_read.f90#L44).
