---
description: "Calendar year at the reporting boundary in the allocation-transaction files"
---

# yr

**Code reference:** `time%yrc` ([daily](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_pou_output.f90#L29-L49), [monthly](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_pou_output.f90#L85-L105), [yearly](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_pou_output.f90#L143-L163), [average annual](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_pou_output.f90#L198-L218)).

The calendar year on which the row was written. Monthly rows are written on the last day of the month, yearly rows on the last day of the year and average-annual rows on the last day of the simulation, so the date marks the end of the reporting period.

| File group | Position |
| --- | --- |
| MET (`wallo_met_*`) | position 4 in TXT and position 5 in CSV, after an extra `ipou` |
| POD and POR (`wallo_pou_pods_*`, `wallo_pou_pors_*`) | 4; absent from daily CSV rows |

[Back to the allocation-transactions schema](allocation-transactions.md).
