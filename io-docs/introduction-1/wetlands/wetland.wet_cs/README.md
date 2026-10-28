---
description: "This file links wetlands to their pesticide, weir, salt, and general-constituent records."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file links wetlands to their pesticide, weir, salt, and general-constituent records.

SWAT+ looks for `wetland.wet_cs` in the simulation working directory; it is not selected through `file.cio`. See the [wet_read_salt_cs.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/wet_read_salt_cs.f90#L31) reader.

# wetland.wet_cs

The first two lines contain a title and column headings. Each following row contains the fields below, in this order.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [k](k.md) | Record number | integer | n/a | — | — |
| [pst](pst.md) | Name of the pesticide input source linked to this wetland, referencing an entry in pesticide.res | string | n/a | — | — |
| [weir](weir.md) | Name of the weir input source linked to this wetland, referencing an entry in weir.res | string | n/a | — | — |
| [salt](salt.md) | Name of the salt input source linked to this wetland, referencing an entry in the salt_res table | string | n/a | — | — |
| [cs](cs.md) | Name of the constituent input source linked to this wetland, referencing an entry in the cs_res table | string | n/a | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
