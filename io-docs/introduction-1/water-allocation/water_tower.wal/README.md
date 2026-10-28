---
description: "This file defines water towers and their storage, drawdown, and water-loss settings."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file defines water towers and their storage, drawdown, and water-loss settings.

SWAT+ looks for `water_tower.wal` in the simulation working directory; it is not selected through `file.cio`. See the [water_tower_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/water_tower_read.f90#L28) reader.

# water_tower.wal

The file contains a title, the entry count, column headings, and the corresponding data rows shown below.

{% hint style="warning" %}
The current file-loading routine has a repeated-loading issue. A complete file layout does not establish that the model will initialize successfully with it.
{% endhint %}

## Number of records

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [imax](imax.md) | Number of records | integer | n/a | — | — |

## Input values

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [i](i.md) | Record number | integer | n/a | — | — |
| [name](name.md) | Record name | string | n/a | — | — |
| [stor_mx](stor_mx.md) | Maximum storage capacity of the water tower | real | — | — | — |
| [ddown_days](ddown_days.md) | Value representing the number of days to drawdown the storage to zero | real | — | — | — |
| [loss_fr](loss_fr.md) | Water-loss fraction for the object | real | — | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
