---
description: "Links groundwater cells to channels using cell identifiers, bed elevations, channel identifiers, connection lengths, and property zones. Depth-zone and observation selectors are optional trailing columns."
---

# chancell.gw

{% hint style="info" %}
The inspected Editor has an exporter for this filename; generation depends on the relevant feature settings. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Links groundwater cells to channels using cell identifiers, bed elevations, channel identifiers, connection lengths, and property zones. Depth-zone and observation selectors are optional trailing columns.

SWAT+ uses the literal filename `chancell.gw` in the simulation working directory rather than selecting this filename through `file.cio`. It is read by [basin_read_objs.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/basin_read_objs.f90#L52). File-presence requirements and feature conditions are determined by this reader; a missing file is not assumed to be harmless.

The file has a metadata record, a column-header record, then one row per channel-cell connection. The reader splits each row into five required columns and up to two optional columns. Internal text buffers and the earlier counting pass are not additional input columns.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [cell_id](cell_id.md) | Index of the groundwater cell whose state (status, head) is referenced for this channel | integer | n/a | — | — |
| [bed_elev](bed_elev.md) | Bed elevation of the channel, used as the base stage for channel water-surface and head comparisons | real | — | — | — |
| [channel](channel.md) | Identifier of the channel record, used to index channel connectivity and cell lists | integer | n/a | — | — |
| [chan_length](chan_length.md) | Length of the channel segment, used together with channel width to compute flow area | real | — | — | — |
| [chan_zone](chan_zone.md) | Groundwater zone identifier assigned to the channel cell | integer | n/a | — | — |
| [dep_zone](dep_zone.md) | Optional depth-zone index selecting the channel-depth series | integer | n/a | — | — |
| [obs](obs.md) | Optional observation selector for this channel-cell connection | integer | n/a | — | — |

The connection columns are loaded by [gwflow_chan_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_chan_read.f90#L49); the earlier reader counts connections.
