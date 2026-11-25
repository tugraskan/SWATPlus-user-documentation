---
description: "HRU number"
---

# unit

**Code reference:** `j` ([writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_output.f90#L73)).

**Printed header value:** `unit` ([header](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_module.f90#L365)).

The header record stores the name in a 9-character field with a leading blank run and a trailing blank. `j` is the index into the per-HRU records, such as `hnb_d(j)`, written on the same line.

**Type:** integer (format `2i8`). **Unit:** n/a.

[Back to the output table](../hru.md).
