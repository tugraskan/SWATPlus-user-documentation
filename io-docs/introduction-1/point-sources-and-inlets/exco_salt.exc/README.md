---
description: "This file supplies named salt-ion export-coefficient values."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file supplies named salt-ion export-coefficient values.

# exco_salt.exc

The first two lines contain a title and column headings. Each following row contains the fields below, in this order.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [exco_salt_name(ii)](exco_salt_name_ii.md) | Name identifying this salt export-coefficient record | string | n/a | — | — |
| [salt(isalt)](salt_isalt.md) | Export-coefficient value for salt ion isalt | real | — | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
