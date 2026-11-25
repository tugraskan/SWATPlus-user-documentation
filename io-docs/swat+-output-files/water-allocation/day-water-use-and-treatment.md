---
description: "Reporting date with missing-jday row variants"
---

# day

**Code reference:** `time%day_mo` ([daily use TXT](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_use_output.f90#L19); [daily treatment TXT](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_treat_output.f90#L19)). This is day of month at the reporting date, including the end-of-period/final simulation date for longer intervals. It has no physical unit.

Daily TXT writes `jday, mon, day, yr`. Every CSV row and monthly/yearly/AA TXT instead begins `mon, day, yr`: **jday is omitted**, although the printed header retains all four date labels. The actual day value is at position 2 in those rows, rather than printed position 3.

The remaining prefix also differs: use writes name then identifier, while treatment writes identifier then name. See the [water-use](water-use.md) and [water-treatment](water-treatment.md) row variants and routing limitations. Dates identify the row boundary; they do not convert the monthly/yearly diagnostics into daily rates.

[Back to the water-use schema](water-use.md) · [Back to the water-treatment schema](water-treatment.md).
