---
description: "Unheaded net die-off; negative values indicate regrowth"
---

# die_off (unheaded data position 17)

**Code reference:** `hpath_bal(j)%path(ipath)%die_off` ([source](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/path_ls_process.f90#L60)).

There is no printed heading for data position 17. `die_off` is the source component name, not a label present in the output header.

The process routine records the sum of the soil and foliage amounts before their net die-off/regrowth step minus the corresponding amounts afterward. Positive values indicate net loss; negative values indicate net regrowth. This includes the effect of the routine's minimum-level adjustments and is not necessarily a nonnegative gross die-off amount. It is distinct from wash-off between plant and soil.

**Unit:** unresolved. The balance declaration says kg/ha while the constituent pathogen state is annotated cfu; no consistent conversion was established. The neighboring printed kg/h suffix does not establish a physical unit for this unheaded value.

The period-averaging operator assigns only `plant` and `soil`; all other result components retain their zero defaults. Thus the monthly, yearly, and average-annual versions do not preserve this component as a process total. See the [family table](README.md) for the 18-value/15-heading mismatch and average-annual CSV format warning.

[Back to the output table](README.md).
