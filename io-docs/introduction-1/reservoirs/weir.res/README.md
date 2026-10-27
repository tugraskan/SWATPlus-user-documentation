---
description: This file contains the reservoir weir parameters.
---

# weir.res

| Field                    | Description                            |  Type  | Unit | Default | Range |
| ------------------------ | -------------------------------------- | :----: | :--: | :-----: | :---: |
| [name](name.md)          | Name of the reservoir weir record      | string |  n/a |   n/a   |  n/a  |
| [linear\_c](disch_co.md)\* | Weir discharge linear coefficient      |  real  | none |         |       |
| [exp\_k](energy_co.md)\* | Weir discharge exponential coefficient |  real  | none |         |       |
| [width](weir_wd.md)\* | Width of weir                          |  real  |   m  |         |       |
| [height](vel_co.md)\* | Height of weir above reservoir bottom  |  real  |   m  |         |       |

\* Input-file labels marked with an asterisk have different Fortran names: `linear_c` → `res_weir(ires)%c`; `exp_k` → `res_weir(ires)%k`; `width` → `res_weir(ires)%w`; `height` → `res_weir(ires)%h`. [Reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/res_read_weir.f90#L55).
