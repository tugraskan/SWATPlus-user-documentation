---
description: This file specifies which elements a Routing Unit contains.
---

# rout\_unit.def

| Field                         | Description                                                        | Type    |
| ----------------------------- | ------------------------------------------------------------------ | ------- |
| [id](id-rout_unit.def.md)\* | Routing Unit definition ID (read but not used by SWAT+ main (6f515368)) | integer |
| [name](name-rout_unit.def.md) | Name of the Routing Unit                                           | string  |
| [elem\_tot](elem_tot.md)\* | Number of columns to read for list of elements in the Routing Unit | integer |
| [elements](elements.md)\* | First column listing elements in the Routing Unit                  | integer |

\* Input-file labels marked with an asterisk have different Fortran names: `id` → `numb`; `elem_tot` → `nspu`; `elements` → `elem_cnt(isp)`. [Reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/ru_read_elements.f90#L126).
