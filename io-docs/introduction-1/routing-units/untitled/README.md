---
description: >-
  This file references other files specifying the elements that are part of a
  Routing Unit and its topographic and field properties.
---

# rout\_unit.rtu

| Field | Description                                 | Type    |
| ------------------- | ------------------------------------------- | ------- |
| id | ID of the Routing Unit                      | integer |
| name                | Name of the Routing Unit                    | string  |
| [define](define.md) | Routing Unit definition name (read but not used by the model) | string |
| dlr | Delivery ratio name (read but not used by the model) | string |
| [topo](topo.md) | Pointer to the topography file              | string  |
| [field](field.md) | Pointer to the field file                   | string  |
