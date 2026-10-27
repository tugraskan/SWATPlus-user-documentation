---
description: >-
  This file defines which HRUs are elements of the Landscape Units in a SWAT+
  setup.
---

# ls\_unit.def

| Field                       | Description                                                          | Type    |
| --------------------------- | -------------------------------------------------------------------- | ------- |
| [id](id-ls_unit.def.md)\* | ID of the Landscape Unit                                             | integer |
| [name](name-ls_unit.def.md) | Name of the Landscape Unit                                           | string  |
| [area](area.md)\* | Area of the Landscape Unit in hectares                               | real    |
| [elem_tot](elem_tot.md)\* | Number of columns to read for list of elements in the Landscape Unit | integer |
| [elements](elements.md)\* | First column listing elements in the Landscape Unit                  | integer |

\* Input-file labels marked with an asterisk have different Fortran names: `id` → `k`; `area` → `lsu_out(i)%area_ha`; `elem_tot` → `nspu`; `elements` → `elem_cnt(isp)`. [Reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/lsu_read_elements.f90#L70).
