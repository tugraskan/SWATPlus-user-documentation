---
description: "This file identifies the time-series files used for general-constituent recall inputs."
---

{% hint style="warning" %}
Although [`recall_read_cs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read_cs.f90#L43-L241) implements this reader (looking for `cs_recall.rec` in the simulation working directory, not via `file.cio`) and [`command.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L356) invokes [`recall_cs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_cs.f90#L3-L103) when `cs_db%num_cs > 0`, **`recall_read_cs` is not called in SWAT+ main (`6f515368`)**.
{% endhint %}

This file identifies the time-series files used for general-constituent recall inputs.

# cs\_recall.rec

The first two lines contain a title and column headings. Each following row contains the fields below, in this order ([`recall_read_cs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read_cs.f90#L108)).

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [k](k.md) | Record number | integer | n/a | — | — |
| [name](name.md) | Record name; read but not used in calculations | string | n/a | — | — |
| [typ](typ.md) | Recall temporal type code: `1`=daily, `2`=monthly, `3`=yearly, `4`=constant/average annual | integer | n/a | 0 | 1–4 |
| [filename](filename.md) | Name of the input file supplying constituent recall values | string | n/a | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
