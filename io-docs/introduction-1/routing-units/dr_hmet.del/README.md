---
description: "This file supplies named heavy-metal delivery values."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file supplies named heavy-metal delivery values.

# dr_hmet.del

The first two lines contain a title and column headings. Each following row contains the fields below, in this order.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [dr_hmet_name(ii)](dr_hmet_name_ii.md) | Name identifying a heavy metals delivery definition (dr_hmet_name) | string | n/a | — | — |
| [hmet(ihmet)](hmet_ihmet.md) | Heavy metals delivery value (hmet) associated with the named delivery definition | real | — | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
