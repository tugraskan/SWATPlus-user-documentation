---
description: "This file defines water towers and their storage, drawdown, and water-loss settings."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the tables are based on the SWAT+ Fortran source (`6f515368`). A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

{% hint style="warning" %}
In [`water_tower_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_tower_read.f90#L27-L46), the outer `do ... end do` loop lacks an `exit` statement after reading `imax` records, causing repeated reading until end-of-file.
{% endhint %}

This file defines water towers and their storage, drawdown, and water-loss settings.

SWAT+ looks for `water_tower.wal` in the simulation working directory; it is not selected through `file.cio`. See the [`water_tower_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_tower_read.f90#L28) reader.

# water_tower.wal

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
| [stor_mx](stor_mx.md) | Maximum storage capacity of the water tower | real | m^3 | — | — |
| [ddown_days](ddown_days.md) | Number of days to draw down storage to zero | real | days | — | — |
| [loss_fr](loss_fr.md) | Water-loss fraction for the water tower | real | fraction | — | 0–1 |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
