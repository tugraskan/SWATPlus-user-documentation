---
description: "This file supplies named heavy-metal export-coefficient values."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file supplies named heavy-metal export-coefficient values.

# exco_hmet.exc

The first two lines contain a title and column headings. Each following row contains the fields below, in this order.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [exco_hmet_name(ii)](exco_hmet_name_ii.md) | Name identifying a heavy metals hydrograph record (character identifier used to match the exco hmet file to the corresponding exco database entry) | string | n/a | — | — |
| [hmet(ihmet)](hmet_ihmet.md) | Export-coefficient value for heavy metal ihmet | real | — | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
