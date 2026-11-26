---
description: "This file defines water pipes, including their storage, drawdown, and water-loss settings."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the tables are based on the SWAT+ Fortran source (main `6f515368`; the read layout is unchanged on dev `aa4179fe`). A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

{% hint style="warning" %}
In [`water_pipe_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_pipe_read.f90#L31-L56), the outer `do ... end do` loop lacks an `exit` statement, [`water_pipe_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_pipe_read.f90#L43) reads an extra `header` line before every pipe, and [`water_pipe_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_pipe_read.f90#L45) reads `num_aqu` without calling `backspace(107)`, so [`water_pipe_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_pipe_read.f90#L52) reads a second data row per pipe rather than rereading the first row.
{% endhint %}

This file defines water pipes, including their storage, drawdown, and water-loss settings.

SWAT+ looks for `water_pipe.wal` in the simulation working directory; it is not selected through `file.cio`. See the [`water_pipe_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_pipe_read.f90#L32) reader.

# water_pipe.wal

After the title, pipe count, and headings, each pipe iteration in the `6f515368` reader consumes a per-pipe header line and two data rows.

## Number of records

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [imax](imax.md) | Number of records | integer | n/a | — | — |

## Input values

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [i](i.md) | Record number | integer | n/a | — | — |
| [name](name.md) | Record name | string | n/a | — | — |
| [stor_mx](stor_mx.md) | Maximum storage capacity of the pipe object | real | m^3 | — | — |
| [ddown_days](ddown_days.md) | Number of days to draw down storage to zero | real | days | — | — |
| [loss_fr](loss_fr.md) | Water-loss fraction for the pipe | real | fraction | — | 0–1 |
| [num_aqu](num_aqu_2.md) | Number of aquifers receiving pipe seepage | integer | n/a | — | — |
| [aqu_loss_fr(iaq)](aqu_loss_fr_iaq.md) | Seepage fraction assigned to each linked aquifer | real | fraction | — | 0–1 |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
