---
description: >-
  This file supplies named sets of initial pesticide values in HRU soil and
  plants.
---

# pest\_hru.ini

[`pest_hru_aqu_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pest_hru_aqu_read.f90#L20-L67) reads `pest_hru.ini` (listed as `pest_soil` on the `init` row of [**file.cio**](../../master-file-file.cio.md)). The file begins with a title line and a column-header line. Each initialization set consists of a record name row followed by `cs_db%num_pests` pesticide rows matching the pesticide order in [**constituents.cs**](../../constituents/constituents.cs.md). The number of sets is counted by reading one name row plus `cs_db%num_pests` rows per set after the header ([`pest_hru_aqu_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pest_hru_aqu_read.f90#L24-L40)), so every set must have exactly that many pesticide rows and no extra lines between sets. (SWAT+ main expected a header line before each set when counting, so it counted files with several sets wrongly.)

## Parameter-set name

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [name](name.md) | Record name | string | n/a | — | — |

## Pesticide rows

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [titldum](titldum.md) | Leading pesticide label token (read and discarded) | string | n/a | — | — |
| [soil](soil.md) | Initial pesticide concentration in soil | real | mg/kg | — | — |
| [plt](plt.md) | Initial pesticide mass on plant foliage | real | kg/ha | — | — |
