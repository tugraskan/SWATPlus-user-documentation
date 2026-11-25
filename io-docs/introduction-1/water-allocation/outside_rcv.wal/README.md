---
description: "This file defines outside-basin receiving objects for water allocation."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the tables are based on the SWAT+ Fortran source (`6f515368`). A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

{% hint style="warning" %}
In SWAT+ main (`6f515368`), [`water_orcv_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_orcv_read.f90#L1-L54) is never called from [`main.f90.in`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/main.f90.in#L104-L115), `orcv` is never read during simulation, and the outer `do ... end do` loop ([`water_orcv_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_orcv_read.f90#L33-L49)) lacks an `exit` statement.
{% endhint %}

This file defines outside-basin receiving objects for water allocation.

SWAT+ looks for `outside_rcv.wal` in the simulation working directory; it is not selected through `file.cio`. See the [`water_orcv_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_orcv_read.f90#L34) reader.

# outside_rcv.wal

The file contains a title, the entry count, column headings, and the corresponding data rows shown below.

## Number of records

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [imax](imax.md) | Number of records | integer | n/a | — | — |

## Input values

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [i](i.md) | Record number | integer | n/a | — | — |
| [name](name.md) | Record name | string | n/a | — | — |
| [filename](filename.md) | Filename associated with the outside-basin receiving object | string | n/a | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
