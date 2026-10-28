---
description: "This file specifies decision-table rules used for scenario updates."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file specifies decision-table rules used for scenario updates.

SWAT+ looks for `scen_dtl.upd` in the simulation working directory; it is not selected through `file.cio`. See the [cal_cond_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/cal_cond_read.f90#L43) reader.

# scen_dtl.upd

The tables below describe the file’s input entries. Repeat array values for the configured constituents or members; these are not additional fixed columns.

## Input values

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [num_dtls](num_dtls.md) | Number of update rules | integer | n/a | — | — |

## Input values

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [max_hits](max_hits.md) | Maximum number of times the referenced update table is executed during the simulation | integer | n/a | — | — |
| [typ](typ.md) | Type of update table to apply | string | n/a | — | — |
| [dtbl](dtbl.md) | Name of the ruleset in conditional.ctl that schedules when this update is applied | string | n/a | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
