---
description: "This file connects canals to groundwater cells."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file connects canals to groundwater cells.

SWAT+ looks for `gwflow_canal.con` in the simulation working directory; it is not selected through `file.cio`. See the [gwflow_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_read.f90#L1277) reader.

# gwflow_canal.con

The file starts with one title line. Each following canal row contains its identifier and connection count, then one three-value group per connection: cell identifier, connection length, and stage. Do not add a separate column-header line.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [canal_id](canal_id.md) | Index identifying the canal object whose connection detail row is being read | integer | n/a | — | — |
| [obj_tot](obj_tot.md) | Number of connections | integer | n/a | — | — |
| [con_row_buf(j)](con_row_buf_j.md) | Connection cell, length, and stage | real | — | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
