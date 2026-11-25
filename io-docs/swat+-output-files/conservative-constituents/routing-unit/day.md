---
description: "Day of the month"
---

# day

**Code reference:** `time%day_mo` ([writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_cs_output.f90#L48)).

**Printed header value:** `day` ([header](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L508)).

The header record stores the name right-aligned in a 6-character field. The day of the month is derived from `time%day` by the time routine. [Day-of-month derivation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/time_control.f90#L163-L165)

**Type:** integer (format `4i6`). **Unit:** n/a.

[Back to the output table](../routing-unit.md).
