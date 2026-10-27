---
description: >-
  This file references other files specifying the elements that are part of a
  Routing Unit and its topographic and field properties.
---

# rout\_unit.rtu

| Field | Description                                 | Type    |
| ------------------- | ------------------------------------------- | ------- |
| id\* | ID of the Routing Unit                      | integer |
| name                | Name of the Routing Unit                    | string  |
| [define](define.md)\* | Routing Unit definition name (read but not used by the model) | string |
| dlr\* | Delivery ratio name (read but not used by the model) | string |
| [topo](topo.md)\* | Pointer to the topography file              | string  |
| [field](field.md)\* | Pointer to the field file                   | string  |

\* Input-file labels marked with an asterisk have different Fortran names: `id` → `k`; `define` → `ru(i)%dbsc%elem_def`; `dlr` → `ru(i)%dbsc%elem_dr`; `topo` → `ru(i)%dbsc%toposub_db`; `field` → `ru(i)%dbsc%field_db`. [Reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/ru_read.f90#L230).
