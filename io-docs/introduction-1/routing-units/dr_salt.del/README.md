---
description: "This file supplies named salt-ion delivery values."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file supplies named salt-ion delivery values.

# dr_salt.del

The first two lines contain a title and column headings. Each following row contains the fields below, in this order.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [dr_salt_name(ii)](dr_salt_name_ii.md) | Name identifying this salt delivery record | string | n/a | — | — |
| [salt(isalt)](salt_isalt.md) | Delivery value for salt ion isalt | real | — | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
