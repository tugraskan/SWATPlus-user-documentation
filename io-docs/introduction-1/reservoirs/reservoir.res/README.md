---
description: >-
  This file contains pointers referencing several files that specify the
  reservoir properties.
---

# reservoir.res

| Field                     | Description                                                      | Type    |
| ------------------------- | ---------------------------------------------------------------- | ------- |
| [id](id-reservoir.res.md)\* | ID of the reservoir                                              | integer |
| [name](name.md)           | Name of the reservoir                                            | string  |
| [init](init.md)​          | Pointer to the reservoir and wetland initialization file         | string  |
| [hyd​](hyd.md)            | Pointer to the reservoir hydrology file                          | string  |
| [rel​](rel.md)\* | Name of the reservoir release decision table or control table | string |
| [sed](sed.md)​            | Pointer to the reservoir and wetland sediment file               | string  |
| [nut​](nut.md)            | Pointer to the reservoir and wetland nutrient file               | string  |

\* Input-file labels marked with an asterisk have different Fortran names: `id` → `k`; `rel` → `res_dat_c(ires)%release`. [Reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/res_read.f90#L74).
