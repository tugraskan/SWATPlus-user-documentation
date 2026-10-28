---
description: "This file links reservoirs to their pesticide, weir, salt, and general-constituent records."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file links reservoirs to their pesticide, weir, salt, and general-constituent records.

SWAT+ looks for `reservoir.res_cs` in the simulation working directory; it is not selected through `file.cio`. See the [res_read_salt_cs.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/res_read_salt_cs.f90#L31) reader.

# reservoir.res_cs

The tables below describe the file’s input entries. Repeat array values for the configured constituents or members; these are not additional fixed columns.


| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [k](k.md) | Record number | integer | n/a | — | — |
| [pst](pst.md) | Name of the pesticide input file (pesticide.res) linked to this reservoir | string | n/a | — | — |
| [weir](weir.md) | Name of the weir input file (weir.res) linked to this reservoir, added by Jaehak 2022 | string | n/a | — | — |
| [salt](salt.md) | Name of the salt input file (salt_res) linked to this reservoir | string | n/a | — | — |
| [cs](cs.md) | Name of the constituent input file (cs_res) linked to this reservoir | string | n/a | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
