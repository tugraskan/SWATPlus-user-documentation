---
description: This file specifies which elements a Routing Unit contains.
---

# rout\_unit.def

This file defines the list of elements belonging to each Routing Unit, read by [`ru_read_elements.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_read_elements.f90#L92-L171).

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [id](id-rout_unit.def.md) | Routing Unit definition ID (read but not used by SWAT+ main (6f515368)) | integer |  |  |  |
| [name](name-rout_unit.def.md) | Name of the Routing Unit | string |  |  |  |
| [elem\_tot](elem_tot.md) | Number of columns to read for list of elements in the Routing Unit | integer |  |  |  |
| [elements](elements.md) | First column listing elements in the Routing Unit | integer |  |  |  |
