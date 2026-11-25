---
description: "Plant-application component under a mismatched decay heading"
---

# decay_kg/h

**Code reference:** `hpath_bal(j)%path(ipath)%apply_plt` ([declaration/default](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_ls_pathogen_module.f90#L15); [write order](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_pathogen_output.f90#L35)).

Despite the printed decay heading, this position writes the plant-application component. Actual net die-off is the unheaded value in data position 17; see [die_off](die_off.md). No active producer was identified for this component in the inspected source, so the declared zero default does not demonstrate a measured process amount.

**Unit:** unresolved. The printed heading says `kg/h`, the balance declaration says `kg/ha`, and the underlying constituent state is annotated `cfu`. The inspected code does not establish a consistent conversion between these bases; do not read the printed suffix as a verified per-hour rate.

The period-averaging operator assigns only `plant` and `soil`; all other result components retain their zero defaults. Thus the monthly, yearly, and average-annual versions do not preserve this component as a process total. See the [family table](README.md) for the 18-value/15-heading mismatch and average-annual CSV format warning.

[Back to the output table](README.md).
