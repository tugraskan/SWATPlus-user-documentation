---
description: "Unheaded regrowth component with no identified producer"
---

# regro (unheaded data position 16)

**Code reference:** `hpath_bal(j)%path(ipath)%regro` ([source](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_ls_pathogen_module.f90#L16)).

There is no printed heading for data position 16. `regro` is the source component name, not a label present in the output header.

No active producer was identified for this separate regrowth component; it retains its declared zero default. Net regrowth can instead appear as a negative value in the separately written `die_off` component.

**Unit:** unresolved. The balance declaration says kg/ha while the constituent pathogen state is annotated cfu; no consistent conversion was established. The neighboring printed kg/h suffix does not establish a physical unit for this unheaded value.

The period-averaging operator assigns only `plant` and `soil`; all other result components retain their zero defaults. Thus the monthly, yearly, and average-annual versions do not preserve this component as a process total. See the [family table](README.md) for the 18-value/15-heading mismatch and average-annual CSV format warning.

[Back to the output table](README.md).
