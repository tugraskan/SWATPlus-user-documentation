---
description: "Recall object nitrate nitrogen"
---

# no3

**Code reference:** `rec_d(irec)%no3` and `brec_d%no3` ([daily writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_output.f90#L23); [declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L36)).

Nitrate nitrogen in the Recall hydrograph. A negative daily volume can trigger nitrate removal from channel storage. The nitrate removed from the channel is not assigned to this field. [Input time basis and diversions](individual-recall.md#how-recall-inputs-become-daily-output).

**Unit:** kg N.

Daily volume and constituent mass values are added into monthly and yearly totals; the average-annual record divides accumulated volume and masses by `time%yrs_prt`. The [hydrograph operators](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L1337) combine temperature by water-volume weighting, and division by years leaves temperature unchanged. The writers perform no volume-to-rate conversion. The basin record sums recall objects. The [family warning](README.md) describes the missing year in `recall_aa.csv` and the extra empty heading in basin CSV output.

[Back to the Individual Recall schema](individual-recall.md); [Basin Recall schema](basin-recall.md).
