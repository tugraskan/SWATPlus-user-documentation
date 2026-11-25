---
description: "This file links named export-coefficient sets to their constituent records."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file links named export-coefficient sets to their organic/mineral, pesticide, pathogen, heavy-metal, and salt records. SWAT+ selects it from `file.cio` (`in_exco%exco`, default `"exco.exc"`) and reads it with [`exco_db_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/exco_db_read.f90#L22-L63).

Despite the `_file` suffix in the Fortran field names, `om_file`, `pest_file`, `path_file`, `hmet_file`, and `salts_file` store **record names** matching the first column of [`exco_om.exc`](../exco_om.exc/README.md), [`exco_pest.exc`](../exco_pest.exc/README.md), [`exco_path.exc`](../exco_path.exc/README.md), [`exco_hmet.exc`](../exco_hmet.exc/README.md), and [`exco_salt.exc`](../exco_salt.exc/README.md), respectively (or `"null"` when a constituent group is unused). Constituent EXCO files are only read when the corresponding count in [`constituents.cs`](../../constituents/constituents.cs.md) is greater than zero ([`exco_db_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/exco_db_read.f90#L57-L60)). Note that [`exco_read_om.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/exco_read_om.f90#L68) matches across `1..db_mx%exco_om` rather than `db_mx%exco`.

# exco.exc

The first two lines contain a title and column headings. Each following row contains the fields below, in this order ([`exco_db_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/exco_db_read.f90#L47)).

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [name](name.md) | Export-coefficient set name | string | n/a | — | — |
| [om\_file](om_file.md) | Record name in `exco_om.exc` linked to this set | string | n/a | — | — |
| [pest\_file](pest_file.md) | Record name in `exco_pest.exc` linked to this set (or `"null"`) | string | n/a | — | — |
| [path\_file](path_file.md) | Record name in `exco_path.exc` linked to this set (or `"null"`) | string | n/a | — | — |
| [hmet\_file](hmet_file.md) | Record name in `exco_hmet.exc` linked to this set (or `"null"`) | string | n/a | — | — |
| [salts\_file](salts_file.md) | Record name in `exco_salt.exc` linked to this set (or `"null"`) | string | n/a | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
