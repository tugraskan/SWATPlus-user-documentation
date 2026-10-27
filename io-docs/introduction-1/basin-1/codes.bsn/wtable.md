---
description: Water table depth algorithm code
---

# wtable

**Code reference:** `bsn_cc%wtdn`

**Declared type:** `basin_control_codes` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/basin_read_cc.f90#L24), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/basin_module.f90#L60)).

| Code | Option                                                                                      |
| ---- | ------------------------------------------------------------------------------------------- |
| 0    | Simulate shallow water table using original water table depth routine (fill to upper limit) |
| 1    | Simulate shallow water table using DRAINMOD water table depth routine                       |
