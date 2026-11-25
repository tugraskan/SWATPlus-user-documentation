---
description: "Sediment-associated pathogen diagnostic, conditionally updated"
---

# sed_kg/h

**Code reference:** `hpath_bal(j)%path(ipath)%sed` ([calculation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/path_ls_runoff.f90#L32)).

The sediment-associated diagnostic is calculated and removed from the surface-soil pathogen pool only when `enratio > 0`. The routine does not reset this field when that condition fails. In the preceding runoff calculation, the runoff diagnostic is overwritten with the nonnegative soil pool and then subtracted, so this sediment term must not be interpreted without that source-order caveat.

**Unit:** unresolved. The printed heading says `kg/h`, the balance declaration says `kg/ha`, and the underlying constituent state is annotated `cfu`. The inspected code does not establish a consistent conversion between these bases; do not read the printed suffix as a verified per-hour rate.

The period-averaging operator assigns only `plant` and `soil`; all other result components retain their zero defaults. Thus the monthly, yearly, and average-annual versions do not preserve this component as a process total. See the [family table](README.md) for the 18-value/15-heading mismatch and average-annual CSV format warning.

[Back to the output table](README.md).
