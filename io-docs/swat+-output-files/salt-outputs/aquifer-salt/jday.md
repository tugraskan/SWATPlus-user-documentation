---
description: "Julian day"
---

# jday

**Code reference:** `time%day` ([writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_salt_output.f90#L36)).

**Printed header value:** `jday` ([header](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_aquifer.f90#L37)).

The header record stores the name right-aligned in a 6-character field. The time routine derives the month and day of the month from `time%day`, so it is the day of the year. [Month and day derivation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/time_control.f90#L163-L165)

**Type:** integer (format `4i6`). **Unit:** n/a.

[Back to the output table](../aquifer-salt.md).
