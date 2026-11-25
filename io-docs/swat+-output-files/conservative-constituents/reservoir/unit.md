---
description: "Reservoir number"
---

# unit

**Code reference:** `j` ([writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_cs_output.f90#L44)).

**Printed header value:** `unit` ([header](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_cs_module.f90#L62)).

The header record stores the name in an 8-character field with surrounding blanks. `j` is the argument of the output routine, and the object index is `iob = sp_ob1%res + j - 1`, so `j` counts the reservoirs. [Object index](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_cs_output.f90#L24)

**Type:** integer (format `2i8`). **Unit:** n/a.

[Back to the output table](../reservoir.md).
