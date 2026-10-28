---
description: "This file supplies named sets of initial general-constituent values for aquifers."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file supplies named sets of initial general-constituent values for aquifers.

SWAT+ looks for `cs_aqu.ini` in the simulation working directory; it is not selected through `file.cio`. See the [cs_aqu_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/cs_aqu_read.f90#L23) reader.

# cs_aqu.ini

The first two lines contain a title and column headings. Each following row contains the fields below, in this order.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | Record name | string | n/a | — | — |
| [aqu](aqu.md) | Concentration, sorbed mass at start of simulation | real | — | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
