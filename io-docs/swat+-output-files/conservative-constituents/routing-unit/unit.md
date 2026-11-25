---
description: "Routing unit number"
---

# unit

**Code reference:** `iru` ([writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_cs_output.f90#L48)).

**Printed header value:** `unit` ([header](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L510)).

The header record stores the name in an 8-character field with surrounding blanks. `iru` is the argument of the output routine, and the object index is `iob = sp_ob1%ru + iru - 1`, so `iru` counts the routing units. [Object index](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_cs_output.f90#L19)

**Type:** integer (format `2i8`). **Unit:** n/a.

[Back to the output table](../routing-unit.md).
