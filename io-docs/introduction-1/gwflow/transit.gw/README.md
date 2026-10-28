---
description: "This file identifies groundwater transit cells in a structured grid."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file identifies groundwater transit cells in a structured grid.

SWAT+ looks for `transit.gw` in the simulation working directory; it is not selected through `file.cio`. See the [gwflow_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_read.f90#L2262) reader.

# transit.gw

After the title and column headings, supply the transit-cell count followed by the cell identifiers.

## Transit-cell count

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [gw_transit_num](gw_transit_num.md) | Count of groundwater transit cells to be read from the file | integer | n/a | — | — |

## Transit cells

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [cell_transit](cell_transit.md) | Cell identifier indexing into the structured grid's cell list for one transit cell entry | integer | n/a | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
