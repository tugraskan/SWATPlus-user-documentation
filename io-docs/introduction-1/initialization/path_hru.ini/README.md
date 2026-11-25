---
description: "This file supplies named sets of initial pathogen values in HRU soil and plants."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file supplies named sets of initial pathogen values in HRU soil and plants.

[`path_hru_aqu_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/path_hru_aqu_read.f90#L23-L61) reads `path_hru.ini` (listed as `path_soil` on the `init` row of [**file.cio**](../../master-file-file.cio.md)).

# path\_hru.ini

After the title and column headings, enter each initial-set name followed by a labeled row containing the soil and plant values for the configured pathogens.

## Parameter-set name

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [name](name.md) | Record name | string | n/a | — | — |

## Input values

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [titldum](titldum.md) | Record label | string | n/a | — | — |
| [soil](soil.md) | Initial soil-compartment value for each pathogen | real | `#cfu/m^2` | — | — |
| [plt](plt.md) | Initial plant-compartment value for each pathogen | real | `#cfu/m^2` | — | — |

{% hint style="warning" %}
The counting pass ([`path_hru_aqu_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/path_hru_aqu_read.f90#L27-L37)) loops `ipath = 1, cs_db%num_paths` to skip one line per pathogen after each name, whereas the loading pass ([`path_hru_aqu_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/path_hru_aqu_read.f90#L53-L60)) reads `header`, `name`, and a single list-directed read (`titldum`, `path_soil_ini(ipathi)%soil`, `path_soil_ini(ipathi)%plt`).
{% endhint %}

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
