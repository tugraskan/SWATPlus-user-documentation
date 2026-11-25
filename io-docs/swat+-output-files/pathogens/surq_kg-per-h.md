---
description: "Surface-runoff diagnostic overwritten with the nonnegative soil pool"
---

# surq_kg/h

**Code reference:** `hpath_bal(j)%path(ipath)%surq = Max(cs_soil(j)%ly(1)%path(ipath), 0.)` ([assignment sequence](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/path_ls_runoff.f90#L24)).

The routine first computes a runoff amount and caps it to the available surface-soil pathogen pool. It then overwrites that result with the entire nonnegative surface-soil pool and subtracts it from the soil. The printed diagnostic follows this overwrite, rather than the preceding capped runoff formula. This documents the assigned value without endorsing the transport calculation.

The surface hydrograph writes zero into its pathogen field, so this diagnostic does not measure what the HRU transmits downstream. [surface hydrograph assignment](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_hyds.f90#L92-L96).

**Unit:** unresolved. The printed heading says `kg/h`, the balance declaration says `kg/ha`, and the underlying constituent state is annotated `cfu`. The inspected code does not establish a consistent conversion between these bases; do not read the printed suffix as a verified per-hour rate.

The period-averaging operator assigns only `plant` and `soil`; all other result components retain their zero defaults. Thus the monthly, yearly, and average-annual versions do not preserve this component as a process total. See the [family table](README.md) for the 18-value/15-heading mismatch and average-annual CSV format warning.

[Back to the output table](README.md).
