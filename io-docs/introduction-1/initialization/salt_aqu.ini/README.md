---
description: "This file supplies named sets of initial salt concentrations and mineral fractions for aquifers."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file supplies named sets of initial salt concentrations and mineral fractions for aquifers.

SWAT+ looks for `salt_aqu.ini` in the simulation working directory; it is not selected through `file.cio`. See the [salt_aqu_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/salt_aqu_read.f90#L23) reader.

# salt_aqu.ini

The first two lines contain a title and column headings. Each following row contains the fields below, in this order.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | Record name | string | n/a | — | — |
| [conc](conc.md) | Salt ion concentration at the start of the simulation | real | — | — | — |
| [frac](frac.md) | Salt mineral fractions at the start of the simulation | real | — | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
