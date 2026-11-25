---
description: "This file supplies named sets of initial pathogen values in water and benthic compartments."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file supplies named sets of initial pathogen values in water and benthic compartments.

[`path_cha_res_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/path_cha_res_read.f90#L27-L66) reads `path_water.ini` (listed as `path_water` on the `init` row of [**file.cio**](../../master-file-file.cio.md)).

# path\_water.ini

After the title and column headings, enter each initial-set name followed by a labeled row containing the water and benthic values for the configured pathogens.

## Parameter-set name

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [path\_init\_name(ipathi)](path_init_name_ipathi.md) | Name identifying this initial pathogen set | string | n/a | — | — |

## Input values

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [titldum](titldum.md) | Record label | string | n/a | — | — |
| [water](water.md) | Initial water-compartment value for each pathogen (copied, but not read in simulation) | real | — | — | — |
| [benthic](benthic.md) | Initial benthic-compartment value for each pathogen (copied, but not read in simulation) | real | — | — | — |

{% hint style="warning" %}
The counting pass ([`path_cha_res_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/path_cha_res_read.f90#L33-L43)) reads one name record followed by two records per pathogen (`2 * cs_db%num_paths`), whereas the loading pass ([`path_cha_res_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/path_cha_res_read.f90#L58-L65)) reads `header`, `path_init_name`, and a single list-directed read (`titldum`, `water`, `benthic`). Furthermore, the downstream `ch_water%path`, `ch_benthic%path`, `res_water%path`, and `res_benthic%path` arrays are not read in simulation calculations in SWAT+ main (`6f515368`).
{% endhint %}

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
