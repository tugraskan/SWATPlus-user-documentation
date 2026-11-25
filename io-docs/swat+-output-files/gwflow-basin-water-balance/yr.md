---
description: "Calendar year"
---

# yr

**Code reference:** `time%yrc` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/time_module.f90#L21)).

The calendar year associated with the output row.

For average-annual output, the printed date is the final reporting date; the basin average-annual values divide the simulation accumulators by `time%nbyr`, the configured simulation-year count. This differs from the `time%yrs_prt` convention used by some other output families.

This is an identifier, label, or date component; it has no physical unit.

[Back to the daily schema](daily-basin-water-balance.md) · [Back to the longer-period schema](longer-period-basin-water-balance.md).
