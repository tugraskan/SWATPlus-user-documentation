---
description: >-
  This file references other files specifying the elements that are part of a
  Routing Unit and its topographic and field properties.
---

# rout\_unit.rtu

This file defines Routing Unit records and links each Routing Unit to its topography and field properties, read by [`ru_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_read.f90#L230).

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [id](id-rout_unit.rtu.md) | ID of the Routing Unit | integer |  |  |  |
| [name](name-rout_unit.rtu.md) | Name of the Routing Unit (read but not used by the model) | string |  |  |  |
| [define](define.md) | Routing Unit definition name (read but not used by the model) | string |  |  |  |
| [dlr](dlr.md) | Delivery ratio name (read but not used by the model) | string |  |  |  |
| [topo](topo.md) | Pointer to the topography file | string |  |  |  |
| [field](field.md) | Pointer to the field file | string |  |  |  |
