---
description: "This file groups groundwater cells for surface-water interactions."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file groups groundwater cells for surface-water interactions.

SWAT+ looks for `sw_group.gw` in the simulation working directory; it is not selected through `file.cio`. See the [gwflow_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_read.f90#L2307) reader.

# sw_group.gw

After the title and column headings, enter one group per row: a label, the number of cells, and that many cell identifiers. Group order determines the group index.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [group_id](group_id.md) | Leading group label for the channel_cell_group record; serves as a human-readable identifier for the group | string | n/a | — | — |
| [ncell](ncell.md) | Number of cell identifiers following this value in the record | integer | n/a | — | — |
| [cell_id](cell_id.md) | Cell identifier repeated ncell times; identifies a member cell of the group | integer | n/a | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
