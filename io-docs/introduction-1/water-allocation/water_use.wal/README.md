---
description: "This file defines water-use objects and their storage, water-loss, and constituent settings."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the tables are based on the SWAT+ Fortran source (main `6f515368`; the read layout is unchanged on dev `aa4179fe`). A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

{% hint style="info" %}
On SWAT+ main the reader left its inner record loop after the first record, so only one water-use record was read. SWAT+ dev removed that `exit` ([`water_use_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_use_read.f90#L34-L102)): all `imax` records are read, and the outer loop ends at the end of the file.
{% endhint %}

This file defines water-use objects and their storage, water-loss, and constituent settings.

SWAT+ looks for `water_use.wal` in the simulation working directory; it is not selected through `file.cio`. See the [`water_use_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_use_read.f90#L35) reader.

# water_use.wal

After the title, object count, and headings, enter one object definition per row. Include the additional pesticide and pathogen rows when those constituents are active.

## Object count

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [imax](imax.md) | Number of records | integer | n/a | — | — |

## Water-use objects

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [name](name.md) | Record name | string | n/a | — | — |
| [stor_mx](stor_mx.md) | Maximum storage capacity of the water-use object | real | m^3 | — | — |
| [lag_days](lag_days.md) | Water-use lag time before outflow occurs | real | days | — | — |
| [loss_fr](loss_fr.md) | Fraction of water lost during use | real | fraction | — | 0–1 |
| [org_min_typ](org_min_typ.md) | Source type for organic/mineral effluent (`const`, `dtbl`, or `recall`) | string | n/a | — | `const`, `dtbl`, `recall` |
| [org_min_name](org_min_name.md) | Name of the organic/mineral record, decision table, or recall object | string | n/a | — | — |
| [pests_typ](pests_typ.md) | Source type for pesticide concentrations (`const`, `dtbl`, or `recall`) | string | n/a | — | — |
| [pests_name](pests_name.md) | Name of the pesticide source record | string | n/a | — | — |
| [paths_typ](paths_typ.md) | Source type for pathogen concentrations (`const`, `dtbl`, or `recall`) | string | n/a | — | — |
| [paths_name](paths_name.md) | Name of the pathogen source record | string | n/a | — | — |
| [salts_typ](salts_typ.md) | Source type for salt ion concentrations (`const`, `dtbl`, or `recall`) | string | n/a | — | — |
| [salts_name](salts_name.md) | Name of the salt source record | string | n/a | — | — |
| [constit_typ](constit_typ.md) | Source type for other constituent concentrations (`const`, `dtbl`, or `recall`) | string | n/a | — | — |
| [constit_name](constit_name.md) | Name of the general-constituent source record | string | n/a | — | — |
| [descrip](descrip.md) | Description of the water-use object | string | n/a | — | — |

## Pesticide values

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [pest](pest.md) | Pesticide concentration of water-use effluent when pesticides are active | real | ppm | 0. | — |

## Pathogen values

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [path](path.md) | Pathogen concentration of water-use effluent when pathogens are active | real | cfu | 0. | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
