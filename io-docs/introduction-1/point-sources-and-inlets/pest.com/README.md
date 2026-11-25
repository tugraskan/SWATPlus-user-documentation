---
description: "This file identifies the recall data used for pesticide inputs."
---

{% hint style="warning" %}
In SWAT+ main (`6f515368`), the `pest.com` reader in [`recall_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read.f90#L205-L276) is provisional/defective: line [`#L265`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read.f90#L265) reads into `recall(i)%hd` (an organic/mineral record) rather than `rec_pest(i)%hd_pest`, and `rec_pest%hd_pest` has no downstream uses. For constant pesticide inputs, use [`exco_pest.exc`](../exco_pest.exc/README.md).
{% endhint %}

This file identifies the recall data used for pesticide inputs. SWAT+ looks for `pest.com` in the simulation working directory; it is not selected through `file.cio` ([`recall_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read.f90#L205)).

# pest.com

The file starts with a title and column headings ([`recall_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read.f90#L206-L208)). For each `db_mx%pestcom` entry (`#L224`), the reader reads `ipestcom_db` on its own row (`#L225`) followed by `imax` recall rows (`#L228-L232`).

## Pesticide database entry

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [ipestcom\_db](ipestcom_db.md) | Pesticide database record identifier; read but not used in calculations | integer | n/a | 0 | — |

## Recall entries

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [k](k.md) | Record number | integer | n/a | — | — |
| [name](name.md) | Record name; read but not used in calculations | string | n/a | — | — |
| [typ](typ.md) | Recall temporal type code: `1`=day, `2`=month, `3`=year | integer | n/a | 0 | 1–3 |
| [filename](filename.md) | Name (`character(len=13)`) of the external pesticide recall file | string | n/a | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
