---
description: "This file defines water pipes, including their storage, drawdown, and water-loss settings."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file defines water pipes, including their storage, drawdown, and water-loss settings.

SWAT+ looks for `water_pipe.wal` in the simulation working directory; it is not selected through `file.cio`. See the [water_pipe_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/water_pipe_read.f90#L32) reader.

# water_pipe.wal

After the title, pipe count, and headings, enter one row per pipe. Put its aquifer loss fractions at the end of that same row; the number of fractions is given by num_aqu.

## Number of records

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [imax](imax.md) | Number of records | integer | n/a | — | — |

## Input values

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [i](i.md) | Record number | integer | n/a | — | — |
| [name](name.md) | Record name | string | n/a | — | — |
| [stor_mx](stor_mx.md) | Maximum storage capacity of the pipe object | real | — | — | — |
| [ddown_days](ddown_days.md) | Value representing the number of days to draw down the storage to zero | real | — | — | — |
| [loss_fr](loss_fr.md) | Water-loss fraction for the object | real | — | — | — |
| [num_aqu](num_aqu_2.md) | Count of aquifers associated with the pipe or tower | integer | n/a | — | — |
| [aqu_loss_fr(iaq)](aqu_loss_fr_iaq.md) | Loss fraction applied to each aquifer linked to the pipe or tower | real | — | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
