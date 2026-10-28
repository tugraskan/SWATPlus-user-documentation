---
description: "This file selects groundwater head output dates and observation cells."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file selects groundwater head output dates and observation cells.

SWAT+ looks for `outputs.gw` in the simulation working directory; it is not selected through `file.cio`. See the [gwflow_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_read.f90#L575) reader.

# outputs.gw

After the title and column headings, enter one keyword and one value per row. Choose the appropriate row type below; the three types are alternatives and need not all appear.

## Head output date

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [record_type](record_type.md) | Literal record type head_output_time | string | n/a | — | — |
| [value](value.md) | Encoding year and day for a groundwater head output time | integer | n/a | — | — |

## Observation cell

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [record_type](record_type.md) | Literal record type observation_cell | string | n/a | — | — |
| [value](value_2.md) | Cell identifier selected for groundwater observation output | integer | n/a | — | — |

## Detailed-output cell

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [record_type](record_type.md) | Literal record type detail_debug_cell | string | n/a | — | — |
| [value](value_3.md) | Cell identifier selected for detailed groundwater debugging output | integer | n/a | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
