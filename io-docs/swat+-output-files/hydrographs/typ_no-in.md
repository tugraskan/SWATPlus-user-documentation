---
description: "ID of the source object"
---

# typ_no

**Code reference:** `ob(icmd)%obtypno_in(iin)` ([daily writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydin_output.f90#L20)).

ID of the source object.

This identifier has no physical unit.

The value identifies the connection shown in this row. Important: the [yearly CSV write](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydin_output.f90#L55) inserts an extra receiving-object number after `type`, giving 29 values under 28 headings. Use the matching TXT or repair the CSV layout before interpreting later columns.

[Back to the output table](README.md).
