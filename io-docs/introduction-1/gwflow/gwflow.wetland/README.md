---
description: "This file supplies wetland-bed thicknesses for groundwater exchange."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file supplies wetland-bed thicknesses for groundwater exchange.

SWAT+ looks for `gwflow.wetland` in the simulation working directory; it is not selected through `file.cio`. See the [wet_read_hyd.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/wet_read_hyd.f90#L80) reader.

# gwflow.wetland

The first two lines contain a title and column headings. Each following row contains the fields below, in this order.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [wet_name](wet_name.md) | Identifier of the wetland (character string) read from the gwflow.wetland file | string | n/a | — | — |
| [thick_val](thick_val.md) | Wetland-bed thickness | real | — | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
