---
description: "Recall water volume"
---

# flo

**Code reference:** `rec_d(irec)%flo` and `brec_d%flo` ([daily writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_output.f90#L23); [declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L32)).

Recall water volume. For monthly and yearly input types, the full selected input value is copied into each daily record. The period totals then add those repeated values. [Input time basis](individual-recall.md#how-recall-inputs-become-daily-output).

**Unit:** m3.

Daily volume and constituent mass values are added into monthly and yearly totals; the average-annual record divides accumulated volume and masses by `time%yrs_prt`. The [hydrograph operators](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L1337) combine temperature by water-volume weighting, and division by years leaves temperature unchanged. The writers perform no volume-to-rate conversion. The printed units row says `m^3/s`; the source component is volume, and the writer applies no division by 86400. The basin record sums recall objects. The [family warning](README.md) describes the missing year in `recall_aa.csv` and the extra empty heading in basin CSV output.

[Back to the Individual Recall schema](individual-recall.md); [Basin Recall schema](basin-recall.md).
