---
description: "This file defines water treatment plants and their treatment levels."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the tables are based on the SWAT+ Fortran source (main `6f515368`; the read layout is unchanged on dev `aa4179fe`). A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

{% hint style="warning" %}
In [`water_treatment_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_treatment_read.f90#L33-L118), the outer `do ... end do` loop lacks an `exit` statement, [`water_treatment_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_treatment_read.f90#L91-L99) runs a secondary `dtbl_flo` lookup whenever `org_min_name /= "null"`, and [`water_treatment_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_treatment_read.f90#L102-L113) reads `pest` and `path` headers/values inside the `itrt = 1, num_treats` loop.
{% endhint %}

This file defines water treatment plants and their treatment levels.

SWAT+ looks for `water_treat.wal` in the simulation working directory; it is not selected through `file.cio`. See the [`water_treatment_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_treatment_read.f90#L34) reader.

# water_treat.wal

After the title, plant count, and headings, enter each plant definition followed by `num_treats` treatment-level rows. Include additional pesticide or pathogen rows inside each treatment-level iteration when those constituents are active.

## Plant count

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [imax](imax.md) | Number of records | integer | n/a | — | — |

## Treatment plants

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [name](name.md) | Record name | string | n/a | — | — |
| [stor_mx](stor_mx.md) | Maximum storage capacity of the treatment plant | real | m^3 | — | — |
| [lag_days](lag_days.md) | Lag time applied to treated outflow from the plant | real | days | — | — |
| [loss_fr](loss_fr.md) | Fraction of water lost during treatment | real | fraction | — | 0–1 |
| [num_treats](num_treats.md) | Number of treatment levels defined for this plant | integer | n/a | 0 | — |

## Treatment levels

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [org_min_typ](org_min_typ.md) | Source type for organic/mineral treatment (`const`, `dtbl`, or `recall`) | string | n/a | — | `const`, `dtbl`, `recall` |
| [org_min_name](org_min_name.md) | Name of the organic/mineral record, decision table, or recall object | string | n/a | — | — |
| [pests_typ](pests_typ.md) | Source type for pesticide removal (`const`, `dtbl`, or `recall`) | string | n/a | — | — |
| [pests_name](pests_name.md) | Name of the pesticide source record | string | n/a | — | — |
| [paths_typ](paths_typ.md) | Source type for pathogen removal (`const`, `dtbl`, or `recall`) | string | n/a | — | — |
| [paths_name](paths_name.md) | Name of the pathogen source record | string | n/a | — | — |
| [salts_typ](salts_typ.md) | Source type for salt ion removal (`const`, `dtbl`, or `recall`) | string | n/a | — | — |
| [salts_name](salts_name.md) | Name of the salt source record | string | n/a | — | — |
| [constit_typ](constit_typ.md) | Source type for other constituent removal (`const`, `dtbl`, or `recall`) | string | n/a | — | — |
| [constit_name](constit_name.md) | Name of the general-constituent source record | string | n/a | — | — |
| [descrip](descrip.md) | Descriptive text for the treatment plant | string | n/a | — | — |

## Pesticide values

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [pest](pest.md) | Pesticide concentration of treated water when pesticides are active | real | ppm | 0. | — |

## Pathogen values

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [path](path.md) | Pathogen concentration of treated water when pathogens are active | real | cfu | 0. | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
