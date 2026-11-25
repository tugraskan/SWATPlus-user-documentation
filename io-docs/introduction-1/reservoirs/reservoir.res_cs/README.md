---
description: "This file links reservoirs to their pesticide, weir, salt, and general-constituent records."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file links reservoirs to their salt and general-constituent records (and also contains columns for pesticide and weir record names).

SWAT+ looks for `reservoir.res_cs` in the simulation working directory; it is not selected through `file.cio`. It skips two header lines and reads one 5-column row per reservoir via [`res_read_salt_cs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_read_salt_cs.f90#L31-L64).

# reservoir.res\_cs

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [k](k.md) | Record number | integer | n/a | — | — |
| [pst](pst.md) | Pesticide input name (read but not used in main 6f515368) | string | n/a | — | — |
| [weir](weir.md) | Weir input name (read but not used in main 6f515368) | string | n/a | — | — |
| [salt](salt.md) | Pointer to the salt record in [salt\_res](../salt_res/) | string | n/a | — | — |
| [cs](cs.md) | Pointer to the constituent record in [cs\_res](../cs_res/) | string | n/a | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
