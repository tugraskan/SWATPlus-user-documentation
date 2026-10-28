---
description: "This file defines outside-basin receiving objects for water allocation."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file defines outside-basin receiving objects for water allocation.

SWAT+ looks for `outside_rcv.wal` in the simulation working directory; it is not selected through `file.cio`. See the [water_orcv_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/water_orcv_read.f90#L34) reader.

# outside_rcv.wal

The file contains a title, the entry count, column headings, and the corresponding data rows shown below.

## Number of records

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [imax](imax.md) | Number of records | integer | n/a | — | — |

## Input values

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [i](i.md) | Record number | integer | n/a | — | — |
| [name](name.md) | Record name | string | n/a | — | — |
| [filename](filename.md) | String specifying the filename associated with the outside basin receiving object | string | n/a | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
