---
description: "This file identifies the time-series files used for salt recall inputs."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file identifies the time-series files used for salt recall inputs.

SWAT+ looks for `salt_recall.rec` in the simulation working directory; it is not selected through `file.cio`. See the [recall_read_salt.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/recall_read_salt.f90#L43) reader.

# salt_recall.rec

The first two lines contain a title and column headings. Each following row contains the fields below, in this order.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [k](k.md) | Record number | integer | n/a | — | — |
| [name](name.md) | Record name | string | n/a | — | — |
| [typ](typ.md) | Recall type selecting the temporal resolution: 1=day, 2=month, 3=year | integer | n/a | — | — |
| [filename](filename.md) | Recall input filename | string | n/a | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
