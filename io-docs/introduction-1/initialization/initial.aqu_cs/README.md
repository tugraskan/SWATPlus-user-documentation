---
description: "This file links an aquifer initial-condition set to its constituent initialization records."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file links an aquifer initial-condition set to its constituent initialization records.

SWAT+ looks for `initial.aqu_cs` in the simulation working directory; it is not selected through `file.cio`. See the [aqu_read_init_cs.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/aqu_read_init_cs.f90#L42) reader.

# initial.aqu_cs

The first two lines contain a title and column headings. Each following row contains the fields below, in this order.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | Record name | string | n/a | — | — |
| [pest](pest.md) | Name of the referenced pesticide initialization record | string | n/a | — | — |
| [path](path.md) | Name of the referenced pathogen initialization record | string | n/a | — | — |
| [hmet](hmet.md) | Name of the referenced heavy-metal initialization record | string | n/a | — | — |
| [salt](salt.md) | Name of the referenced salt initialization record | string | n/a | — | — |
| [cs](cs.md) | Name of the referenced general-constituent initialization record | string | n/a | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
