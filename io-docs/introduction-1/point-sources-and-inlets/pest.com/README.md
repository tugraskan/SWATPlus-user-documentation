---
description: "This file identifies the recall data used for pesticide inputs."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file identifies the recall data used for pesticide inputs.

SWAT+ looks for `pest.com` in the simulation working directory; it is not selected through `file.cio`. See the [recall_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/recall_read.f90#L205) reader.

# pest.com

The file starts with a title and column headings. The current format includes a pesticide database identifier before a block of recall definitions. Each recall definition gives its record number, name, time type, and input filename. The database-identifier arrangement remains provisional; confirm it before preparing a working input file.

## Pesticide database entry

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [ipestcom_db](ipestcom_db.md) | Pesticide database record identifier | integer | n/a | — | — |

## Recall entries

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [k](k.md) | Record number | integer | n/a | — | — |
| [name](name.md) | Record name | string | n/a | — | — |
| [typ](typ.md) | An integer recall type specifying the periodicity of the pesticide application: 1=day, 2=month, 3=year | integer | n/a | — | — |
| [filename](filename.md) | A 13-character name of an external file containing pesticide application data referenced by this recall record | string | n/a | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
