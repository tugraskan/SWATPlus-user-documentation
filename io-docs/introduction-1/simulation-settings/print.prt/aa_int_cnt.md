---
description: Number of print intervals for average annual output (ignored on SWAT+ dev)
---

# aa\_int\_cnt

**Code reference:** none on SWAT+ dev; [`basin_print_codes_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_print_codes_read.f90#L32) reads the first value of line five into a scratch variable and discards it.

SWAT+ dev no longer supports average-annual print intervals. Keep a line here (for example `0`) so that the following lines are read in the right place; its values have no effect. Average-annual output always covers all printed years, after [nyskip](nyskip.md).

{% hint style="info" %}
In SWAT+ main, `aa_int_cnt > 0` followed by that many end years printed average-annual results for each interval. Dev removed this, together with [aa\_yrs](aa_yrs.md).
{% endhint %}
