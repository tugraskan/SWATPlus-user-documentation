---
description: "GIS ID of the routing unit"
---

# gis_id

**Code reference:** `ob(iob)%gis_id` ([writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_cs_output.f90#L48)).

**Printed header value:** `gis_id` ([header](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L511)).

The header record stores the name in a 12-character field with surrounding blanks. The object index is `iob = sp_ob1%ru + iru - 1`, so `ob(iob)` is the object of the routing unit. [Object index](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_cs_output.f90#L19)

**Type:** integer (format `2i8`). **Unit:** n/a.

[Back to the output table](../routing-unit.md).
