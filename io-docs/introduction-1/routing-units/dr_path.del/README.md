---
description: "This file supplies named pathogen delivery values."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file supplies named pathogen delivery values.

# dr_path.del

The first two lines contain a title and column headings. Each following row contains the fields below, in this order.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [dr_path_name(ii)](dr_path_name_ii.md) | Name identifying this pathogen delivery record | string | n/a | — | — |
| [path(ipath)](path_ipath.md) | Delivery value for pathogen ipath | real | — | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
