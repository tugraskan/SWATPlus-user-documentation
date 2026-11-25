---
description: Water table depth algorithm code
---

# wtable

**Code reference:** `bsn_cc%wtdn` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L60), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_cc.f90#L24)).

Selects the shallow water table depth algorithm in [`swr_percmain.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/swr_percmain.f90#L152-L177) (struct default `0`).

| Code | Option |
| ---- | ------ |
| 0 | Simulate shallow water table using original water table depth routine (fill to upper limit) |
| 1 | Simulate shallow water table using DRAINMOD water table depth routine |
