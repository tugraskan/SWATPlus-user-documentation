---
description: "This file supplies named sets of initial general-constituent concentrations for channel water."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file supplies named sets of initial general-constituent concentrations for channel water.

SWAT+ looks for `cs_channel.ini` in the simulation working directory; it is not selected through `file.cio`. See the [cs_cha_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/cs_cha_read.f90#L28) reader.

# cs_channel.ini

The first two lines contain a title and column headings. Each following row contains the fields below, in this order.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | Record name | string | n/a | — | — |
| [conc](conc.md) | Constituent concentration at the start of the simulation | real | — | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
