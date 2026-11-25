---
description: "This file identifies the time-series files used for salt recall inputs."
---

{% hint style="warning" %}
Although [`recall_read_salt.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read_salt.f90#L43-L242) implements this reader (looking for `salt_recall.rec` in the simulation working directory, not via `file.cio`) and [`command.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L355) invokes [`recall_salt.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_salt.f90#L3-L118) when `cs_db%num_salts > 0`, **`recall_read_salt` is not called in SWAT+ main (`6f515368`)**.
{% endhint %}

This file identifies the time-series files used for salt recall inputs.

# salt\_recall.rec

The first two lines contain a title and column headings. Each following row contains the fields below, in this order ([`recall_read_salt.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read_salt.f90#L109)).

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [k](k.md) | Record number | integer | n/a | — | — |
| [name](name.md) | Record name; read but not used in calculations | string | n/a | — | — |
| [typ](typ.md) | Recall temporal type code: `1`=day, `2`=month, `3`=year, `4`=constant/average annual | integer | n/a | 0 | 1–4 |
| [filename](filename.md) | Salt recall input filename | string | n/a | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
