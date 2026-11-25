---
description: "Calendar year"
---

# yr

**Code reference:** `time%yrc` ([writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_cs_output.f90#L49)).

**Printed header value:** `yr` ([header](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cs_module.f90#L184)).

The header record stores the name right-aligned in a 6-character field. The value is the current calendar year of the simulation clock, which starts at `time%yrc_start`. [Clock start](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/time_control.f90#L88)

**Type:** integer (format `4i6`). **Unit:** n/a.

[Back to the output table](../hru.md).
