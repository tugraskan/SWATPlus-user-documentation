---
description: >-
  This file contains pointers referencing several files that specify the wetland
  properties.
---

# wetland.wet

| Field            | Description                                                      | Type    |
| ---------------- | ---------------------------------------------------------------- | ------- |
| [id](numb.md)\* | ID of the wetland                                                | integer |
| [name](name.md)  | Name of the wetland                                              | string  |
| [init​](init.md) | Pointer to the reservoir and wetland initialization file         | string  |
| [hyd​](hyd.md)   | Pointer to the wetland hydrology file                            | string  |
| [rel](rel.md)\* | Pointer to the reservoir and wetland release decision table file | string  |
| [sed](sed.md)    | Pointer to the reservoir and wetland sediment file               | string  |
| [nut](nut.md)    | Pointer to the reservoir and wetland nutrient file               | string  |
| [WEIR](weir.md) | Extra example-file token; not read by SWAT+ main (6f515368) | string |

\* Input-file labels marked with an asterisk have different Fortran names: `id` → `k`; `rel` → `wet_dat_c(ires)%release`. [Reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/wet_read.f90#L66).
