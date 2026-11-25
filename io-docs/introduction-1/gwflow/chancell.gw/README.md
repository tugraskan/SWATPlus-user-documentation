---
description: "Channel-cell connections and their properties."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file connects groundwater cells to SWAT+ channels and gives the properties of each connection. Its presence, together with `gwflow` = 1 in [codes.bsn](../../basin-1/codes.bsn/gwflow.md), turns GWFlow on.

SWAT+ looks for `chancell.gw` in the simulation working directory; it is not selected through `file.cio`. See the [`gwflow_chan_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_chan_read.f90#L34-L76) reader.

# chancell.gw

The first two lines are a title and column headings. Then give one line per channel–cell connection, fields separated by spaces. The first five fields are required; `dep_zone` and `obs` are optional trailing fields, and `obs` can be given only after `dep_zone` ([`gwflow_chan_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_chan_read.f90#L49-L75)).

The number of connections becomes the number of GWFlow objects. When `object.cnt` gives no GWFlow count, SWAT+ counts the lines in this file, skipping three lines before counting, while the reader skips only two. The count is then one short, and the last connection is not read ([`basin_read_objs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_objs.f90#L49-L66)). Until this is fixed, give the count in `object.cnt`. This is listed in `MODEL_ISSUES.md`.

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [cell_id](cell_id.md) | Groundwater cell number | integer | n/a | — | 1 to ncell |
| [bed_elev](bed_elev.md) | Channel bed elevation in the cell | real | m | — | — |
| [channel](channel.md) | SWAT+ channel number | integer | n/a | — | — |
| [chan_length](chan_length.md) | Channel length in the cell | real | m | — | — |
| [chan_zone](chan_zone.md) | Zone for streambed properties | integer | n/a | — | rows of zones.gw |
| [dep_zone](dep_zone.md) | Column of `chan_depth.gw` for this connection (optional) | integer | n/a | 0 | — |
| [obs](obs.md) | 1 = write daily exchange for this connection (optional) | integer | n/a | 0 | 0 or 1 |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
