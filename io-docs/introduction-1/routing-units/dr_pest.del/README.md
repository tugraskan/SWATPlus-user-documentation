---
description: "This file supplies named pesticide delivery values."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file supplies named pesticide delivery values.

# dr_pest.del

The first two lines contain a title and column headings. Each following row contains the fields below, in this order.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [dr_pest_name(ii)](dr_pest_name_ii.md) | Identifier linking this record to a named pesticide delivery definition | string | n/a | — | — |
| [pest(ipest)](pest_ipest.md) | Pesticide delivery value associated with the named pesticide | real | — | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
