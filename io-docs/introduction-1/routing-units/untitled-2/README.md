---
description: This file lists all elements that are part of a Routing Unit.
---

# rout\_unit.ele

This file defines individual Routing Unit elements, their object references, area fractions, and delivery-ratio settings, read by [`ru_read_elements.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_read_elements.f90#L39-L89) (and optionally updated during HRU fraction changes in [`hru_fr_change.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_fr_change.f90#L35-L64)).

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [id](id-rout_unit.ele.md) | ID of the element | integer |  |  |  |
| [name](name-rout_uni.ele.md) | Name of the element | string |  |  |  |
| [obj\_typ](obj_typ.md) | Object type of the element | string |  |  |  |
| [obj\_id](obj_id.md) | Object ID of the element | integer |  |  |  |
| [frac](frac.md) | Fraction/ expansion factor of element in Routing Unit | real |  |  |  |
| [dlr](dlr-rout_unit.ele.md) | Delivery ratio name or calculation keyword for the element | string |  |  |  |
