---
description: "Soil erosion predicted with the USLE equation"
---

# usle

**Code reference:** `bls_d%usle` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_module.f90#L158)).

This field reports the USLE soil erosion estimate. The units record prints `tons`, while the daily calculation is in metric tons per hectare. HRU-LTE sets this field to zero. [USLE calculation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ero_ysed.f90#L81)

**Unit:** t/ha for daily, monthly, and yearly output. Average annual uses t/ha/year.

[Back to the output table](README.md).
