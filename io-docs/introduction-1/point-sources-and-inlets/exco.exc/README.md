---
description: "This file links named export-coefficient sets to their constituent records."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file links named export-coefficient sets to their constituent records.

# exco.exc

The first two lines contain a title and column headings. Each following row contains the fields below, in this order.

{% hint style="warning" %}
The interpretation of these records differs between initialization and direct routing. Confirm the intended routing setup before assigning coefficient or load units.
{% endhint %}

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | Record name | string | n/a | — | — |
| [om_file](om_file.md) | Name of the external Organic Matter (OM) input file linked to this connection record | string | n/a | — | — |
| [pest_file](pest_file.md) | Name of the external Pesticide input file linked to this connection record | string | n/a | — | — |
| [path_file](path_file.md) | Name of the external Pathogen (PATH) input file linked to this connection record | string | n/a | — | — |
| [hmet_file](hmet_file.md) | Name of the associated heavy-metal export-coefficient record | string | n/a | — | — |
| [salts_file](salts_file.md) | Name of the external Salt loading input file linked to this connection record | string | n/a | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
