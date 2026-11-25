---
description: >-
  This file defines which HRUs are elements of the Landscape Units in a SWAT+
  setup.
---

# ls\_unit.def

This file defines the Landscape Units and the element IDs belonging to each unit, read from [`main.f90.in`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/main.f90.in#L69) by [`lsu_read_elements.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/lsu_read_elements.f90#L31-L94) and expanded with [`define_unit_elements.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/define_unit_elements.f90#L1-L96). Line 1 contains a title, line 2 gives the landscape unit count (`mlsu`), line 3 holds column headings, and the remaining `mlsu` rows define each Landscape Unit and its element list.

## Number of landscape units

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [mlsu](mlsu.md) | Number of Landscape Units | integer | n/a | — | — |

## Input values

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [id](id-ls_unit.def.md) | ID of the Landscape Unit | integer | n/a | — | — |
| [name](name-ls_unit.def.md) | Name of the Landscape Unit | string | n/a | — | — |
| [area](area.md) | Area of the Landscape Unit in hectares | real | ha | — | — |
| [elem\_tot](elem_tot.md) | Number of columns to read for list of elements in the Landscape Unit | integer | n/a | — | — |
| [elements](elements.md) | First column listing elements in the Landscape Unit | integer | n/a | — | — |
