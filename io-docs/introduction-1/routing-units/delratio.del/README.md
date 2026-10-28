---
description: "This file links named delivery-ratio sets to their organic/mineral, pesticide, pathogen, heavy-metal, and salt records."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file links named delivery-ratio sets to their organic/mineral, pesticide, pathogen, heavy-metal, and salt records.

# delratio.del

The first two lines contain a title and column headings. Each following row contains the fields below, in this order.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | Record name | string | n/a | — | — |
| [om_file](om_file.md) | Name of the associated organic-mineral (om) file providing source data for this delivery ratio | string | n/a | — | — |
| [pest_file](pest_file.md) | Name of the associated pesticide (pest) file providing source data for this delivery ratio | string | n/a | — | — |
| [path_file](path_file.md) | Name of the associated pathogen (path) file providing source data for this delivery ratio | string | n/a | — | — |
| [hmet_file](hmet_file.md) | Name of the associated heavy-metal delivery record | string | n/a | — | — |
| [salts_file](salts_file.md) | Name of the associated salt (salts) file providing source data for this delivery ratio | string | n/a | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
