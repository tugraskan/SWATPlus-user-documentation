---
description: This file contains the reservoir and wetland sediment parameters.
---

# sediment.res

| Field                                        | Description                                            |  Type  |  Unit | Default |    Range   |
| -------------------------------------------- | ------------------------------------------------------ | :----: | :---: | :-----: | :--------: |
| [name](name.md)                              | Name of the reservoir and wetland sediment record      | string |  n/a  |   n/a   |     n/a    |
| [nsed](nsed.md) | Equilibrium sediment concentration in the reservoir | real | mg/L | 1.0 | 1.0-5000.0 |
| [d50](d50.md)                                | Median particle size of suspended and benthic sediment |  real  |   μm  |   10.0  |            |
| <p><a href="carbon.md">carbon</a></p><p></p> | Organic carbon in suspended and benthic sediment       |  real  |   %   |         |            |
| [bd](bd.md)                                  | Bulk density of benthic sediment                       |  real  | t/m^3 |         |            |
| [sed\_stl](sed_stl.md)\* | Sediment settling rate input (read but not used by the model) | real | n/a | 1.0 |  |
| [stl\_vel](stl_vel.md)\* | Sediment settling velocity input (read but not used by the model) | real | m/d | 1.0 |  |

\* Input-file labels marked with an asterisk have different Fortran names: `sed_stl` → `res_sed(ires)%sed_stlr`; `stl_vel` → `res_sed(ires)%velsetlr`. [Reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/res_read_sed.f90#L55).
