---
description: >-
  This file supplies named sets of initial pesticide values for water and
  benthic sediment.
---

# pest\_water.ini

[`pest_cha_res_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pest_cha_res_read.f90#L24-L67) reads `pest_water.ini` (listed as `pest_water` on the `init` row of [**file.cio**](../../master-file-file.cio.md)). The file begins with a title line and a column-header line. The number of pesticide values per compartment is `cs_db%num_pests`.

## Parameter-set name

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [name](name.md) | Record name | string | n/a | — | — |

## Loading-pass values

After the name row, a single list-directed read requests the following fields in order:

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [titldum](titldum.md) | Leading character label token (read and discarded) | string | n/a | — | — |
| [water](water.md) | Array of `cs_db%num_pests` initial values for water | real | mg/L (channels/aquifers) | — | — |
| [benthic](benthic.md) | Array of `cs_db%num_pests` initial values for benthic sediment | real | mg/L (channels) | — | — |

{% hint style="warning" %}
The counting pass ([`pest_cha_res_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pest_cha_res_read.f90#L33-L43)) and loading pass ([`pest_cha_res_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pest_cha_res_read.f90#L61-L66)) use different record patterns. The counting pass reads one name record followed by two records per pesticide (`2 * cs_db%num_pests`), whereas after rewinding, the loading pass reads the name and then executes a single list-directed read for `titldum`, the complete `water` array, and the complete `benthic` array.
{% endhint %}
