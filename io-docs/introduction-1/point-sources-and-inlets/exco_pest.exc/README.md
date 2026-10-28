---
description: "This file supplies named pesticide export-coefficient values."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file supplies named pesticide export-coefficient values.

# exco_pest.exc

The first two lines contain a title and column headings. Each following row contains the fields below, in this order.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [exco_pest_name(ii)](exco_pest_name_ii.md) | Identifier naming the pesticide hydrograph set associated with this EXCO pest record | string | n/a | — | — |
| [pest(ipest)](pest_ipest.md) | Sequence of pesticide hydrograph values for the named pesticide, as pesticide hydrographs | real | — | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
