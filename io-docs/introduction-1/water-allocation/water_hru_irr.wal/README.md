---
description: "This file groups irrigation HRUs and assigns their irrigation-demand decision tables."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file groups irrigation HRUs and assigns their irrigation-demand decision tables.

SWAT+ looks for `water_hru_irr.wal` in the simulation working directory; it is not selected through `file.cio`. See the [water_hru_irr_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/water_hru_irr_read.f90#L29) reader.

# water_hru_irr.wal

After the title, group count, and headings, enter an irrigation-group name and HRU count. Follow each group with one HRU identifier and demand decision-table name per member.

## Irrigation-group count

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [imax](imax.md) | Number of records | integer | n/a | — | — |

## Irrigation groups

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | Record name | string | n/a | — | — |
| [hrus](hrus.md) | Number of irrigation operations sourced from the irrigation operations file | integer | n/a | — | — |

## Group members

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [hru_num(j)](hru_num_j.md) | HRU number associated with the j-th irrigation operation | integer | n/a | — | — |
| [dtbl_lum(j)](dtbl_lum_j.md) | Name of the decision table used to set daily irrigation demand for the j-th HRU | string | n/a | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
