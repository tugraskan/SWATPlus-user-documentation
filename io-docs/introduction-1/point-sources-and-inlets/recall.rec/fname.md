---
description: Time-series filename or EXCO database record name
---

# fname

**Code reference:** `recall(i)%filename` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L431), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read.f90#L80)).

Character string (`character(len=25)`) identifying the data source for this recall entry:

* For `type` `0`–`3`, `fname` is the filename of the organic/mineral time-series input file opened on unit `108` in [`recall_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read.f90#L89); see [`'om_filename'.rec`](../filename.rec/README.md).
* For `type = 4`, `fname` is matched against `exco_db(iexco_om)%name` from [`exco.exc`](../exco.exc/README.md) in [`recall_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read.f90#L187).

During SWIFT export, [`swift_output.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/swift_output.f90#L264-L269) also writes `recall(irec)%filename` into `SWIFT/recall.swf` and creates average-annual files under `SWIFT/`.
