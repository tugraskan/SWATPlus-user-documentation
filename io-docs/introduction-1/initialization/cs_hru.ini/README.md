---
description: "This file supplies named sets of initial general-constituent values in HRU soil and plants."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file supplies named sets of initial general-constituent values in HRU soil and plants.

SWAT+ looks for `cs_hru.ini` in the simulation working directory; it is not selected through `file.cio`. See the [`cs_hru_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cs_hru_read.f90#L23-L75) reader.

# cs\_hru.ini

The first **5 lines** contain a title and four header lines ([`cs_hru_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cs_hru_read.f90#L24-L32)). For each initial-condition set, enter its `name` row followed by separate `soil` and `plt` rows, each containing `2 * cs_db%num_cs` values (first `cs_db%num_cs` dissolved concentrations, then `cs_db%num_cs` sorbed concentrations, e.g., for `SeO4`, `SeO3`, and `Boron`).

## Parameter-set name

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [name](name.md) | Record name | string | n/a | — | — |

## Soil values

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [soil](soil.md) | Dissolved (`1..num_cs`) and sorbed (`num_cs+1..2*num_cs`) constituent values in soil | real | mg/L; mg/kg | — | — |

## Plant values

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [plt](plt.md) | Intended plant constituent values (read into memory, but not used in simulation) | real | — | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
