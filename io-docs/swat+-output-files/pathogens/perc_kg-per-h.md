---
description: "Pathogen removed from soil layer 1 by the percolation calculation"
---

# perc_kg/h

**Code reference:** `hpath_bal(j)%path(ipath)%perc1` ([calculation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/path_ls_swrouting.f90#L23)).

The calculation scales the surface-soil pathogen pool using layer-1 percolation, caps the result to the available pool, bounds it below by zero, and subtracts it from layer 1. This is not a measured concentration or necessarily export beyond the entire soil profile. The inspected routine does not add the removed amount to a deeper layer.

The separate HRU recharge hydrograph writes zero into its pathogen slot. [recharge hydrograph](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_hyds.f90#L105-L114).

**Unit:** unresolved. The printed heading says `kg/h`, the balance declaration says `kg/ha`, and the underlying constituent state is annotated `cfu`. The inspected code does not establish a consistent conversion between these bases; do not read the printed suffix as a verified per-hour rate.

The period-averaging operator assigns only `plant` and `soil`; all other result components retain their zero defaults. Thus the monthly, yearly, and average-annual versions do not preserve this component as a process total. See the [family table](README.md) for the 18-value/15-heading mismatch and average-annual CSV format warning.

[Back to the output table](README.md).
