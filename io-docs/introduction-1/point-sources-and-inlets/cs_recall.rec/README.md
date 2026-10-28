---
description: "This file identifies the time-series files used for general-constituent recall inputs."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file identifies the time-series files used for general-constituent recall inputs.

SWAT+ looks for `cs_recall.rec` in the simulation working directory; it is not selected through `file.cio`. See the [recall_read_cs.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/recall_read_cs.f90#L43) reader.

# cs_recall.rec

The first two lines contain a title and column headings. Each following row contains the fields below, in this order.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [k](k.md) | Record number | integer | n/a | — | — |
| [name](name.md) | Record name | string | n/a | — | — |
| [typ](typ.md) | Recall temporal type code: 1 for daily, 2 for monthly, or 3 for yearly data | integer | n/a | — | — |
| [filename](filename.md) | Name of the input file supplying constituent recall values | string | n/a | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
