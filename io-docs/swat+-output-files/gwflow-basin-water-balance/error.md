---
description: "Groundwater water-balance closure error"
---

# error

**Code reference:** `mass_error` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_output.f90#L579)).

The daily groundwater balance closure error, expressed as a percentage. It compares ending storage with starting storage plus the signed water exchanges; it is a balance diagnostic, not an additional water flux.

**Unit:** %.

This field appears in the daily file only; it is not a column in the monthly, yearly, or average-annual basin water-balance files.

[Back to the output table](README.md).
