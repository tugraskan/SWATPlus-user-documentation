---
description: "This file links named delivery-ratio sets to their organic/mineral, pesticide, pathogen, heavy-metal, and salt records."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file links named delivery-ratio sets to their organic/mineral, pesticide, pathogen, heavy-metal, and salt records, read by [`dr_db_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dr_db_read.f90#L22-L60). Despite the `_file` suffix in the Fortran field names, `om_file`, `pest_file`, `path_file`, `hmet_file`, and `salts_file` store **record names** matching the first column of [**dr\_om.del**](../dr_om.del/), [**dr\_pest.del**](../dr_pest.del/), [**dr\_path.del**](../dr_path.del/), [**dr\_hmet.del**](../dr_hmet.del/), and [**dr\_salt.del**](../dr_salt.del/), respectively. Constituent delivery files are only read when the corresponding constituent count in [`constituents.cs`](../../constituents/constituents.cs.md) is greater than zero ([`dr_db_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dr_db_read.f90#L57-L60)).

# delratio.del

The first two lines contain a title and column headings. Each following row contains the fields below, in this order.

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [name](name.md) | Record name | string | n/a | — | — |
| [om\_file](om_file.md) | Name of the organic/mineral delivery-ratio record in dr\_om.del | string | n/a | — | — |
| [pest\_file](pest_file.md) | Name of the pesticide delivery-ratio record in dr\_pest.del | string | n/a | — | — |
| [path\_file](path_file.md) | Name of the pathogen delivery-ratio record in dr\_path.del | string | n/a | — | — |
| [hmet\_file](hmet_file.md) | Name of the heavy-metal delivery-ratio record in dr\_hmet.del | string | n/a | — | — |
| [salts\_file](salts_file.md) | Name of the salt-ion delivery-ratio record in dr\_salt.del | string | n/a | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
