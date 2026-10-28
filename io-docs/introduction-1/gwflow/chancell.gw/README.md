---
description: "This file connects groundwater cells to channels and supplies the properties of each connection."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file connects groundwater cells to channels and supplies the properties of each connection.

SWAT+ looks for `chancell.gw` in the simulation working directory; it is not selected through `file.cio`. See the [basin_read_objs.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/basin_read_objs.f90#L52) reader.

# chancell.gw

After the title and column headings, enter one row per groundwater–channel connection. The first five fields are required; the depth-zone and observation selectors are optional trailing fields.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [cell_id](cell_id.md) | Index of the groundwater cell whose state (status, head) is referenced for this channel | integer | n/a | — | — |
| [bed_elev](bed_elev.md) | Bed elevation of the channel | real | — | — | — |
| [channel](channel.md) | Identifier of the channel record | integer | n/a | — | — |
| [chan_length](chan_length.md) | Length of the channel segment | real | — | — | — |
| [chan_zone](chan_zone.md) | Groundwater zone identifier assigned to the channel cell | integer | n/a | — | — |
| [dep_zone](dep_zone.md) | Depth-zone index selecting the channel-depth series | integer | n/a | — | — |
| [obs](obs.md) | Observation selector for this channel-cell connection | integer | n/a | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
