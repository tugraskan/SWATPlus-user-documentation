---
description: "This file defines outside water sources and their constituent inputs."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the tables are based on the SWAT+ Fortran source (main `6f515368`; the read layout is unchanged on dev `aa4179fe`). A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

{% hint style="warning" %}
In [`water_osrc_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_osrc_read.f90#L33-L101), the outer `do ... end do` loop lacks an `exit` statement after reading `imax` records. Only `org_min_typ` and `org_min_name` are evaluated during simulation in SWAT+ main (`6f515368`).
{% endhint %}

This file defines outside water sources and their constituent inputs.

SWAT+ looks for `outside_src.wal` in the simulation working directory; it is not selected through `file.cio`. See the [`water_osrc_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_osrc_read.f90#L34) reader.

# outside_src.wal

After the title, source count, and headings, enter one definition per outside source. Include the additional pesticide and pathogen rows when those constituents are configured.

## Source count

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [imax](imax.md) | Number of records | integer | n/a | — | — |

## Outside sources

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [name](name.md) | Record name | string | n/a | — | — |
| [org_min_typ](org_min_typ.md) | Resolution type for organic/mineral constituent (`const`, `dtbl`, or `recall`) | string | n/a | — | `const`, `dtbl`, `recall` |
| [org_min_name](org_min_name.md) | Name of the organic/mineral record, decision table, or recall object | string | n/a | — | — |
| [pests_typ](pests_typ.md) | Resolution type for pesticide constituent (`const`, `dtbl`, or `recall`) | string | n/a | — | — |
| [pests_name](pests_name.md) | Name of the pesticide source record | string | n/a | — | — |
| [paths_typ](paths_typ.md) | Resolution type for pathogen constituent (`const`, `dtbl`, or `recall`) | string | n/a | — | — |
| [paths_name](paths_name.md) | Name of the pathogen source record | string | n/a | — | — |
| [salts_typ](salts_typ.md) | Resolution type for salt ion constituent (`const`, `dtbl`, or `recall`) | string | n/a | — | — |
| [salts_name](salts_name.md) | Name of the salt source record | string | n/a | — | — |
| [constit_typ](constit_typ.md) | Resolution type for other constituents (`const`, `dtbl`, or `recall`) | string | n/a | — | — |
| [constit_name](constit_name.md) | Name of the general-constituent source record | string | n/a | — | — |
| [descrip](descrip.md) | Free-text description of the outside-source object | string | n/a | — | — |

## Pesticide values

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [pest](pest.md) | Pesticide concentration applied per object when pesticides are active | real | ppm | 0. | — |

## Pathogen values

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [path](path.md) | Pathogen concentration applied per object when pathogens are active | real | cfu | 0. | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
