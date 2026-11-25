---
description: "This file defines points of diversion (PODs) and their associated places of use (POUs)."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the tables are based on the SWAT+ Fortran source (dev `aa4179fe`). A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

{% hint style="warning" %}
In [`water_allocation_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_read.f90#L194), the file-open guard is `if (.not. i_exist .or. in_wallo%pod /= "null")`, which enters the open block whenever `in_wallo%pod` is not `"null"` even if the file is missing.
{% endhint %}

This file defines points of diversion (PODs) and their associated places of use (POUs). The default filename is `point_of_diver.wro`, selected through `in_wallo%pod` in `file.cio` ([`input_file_module.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/input_file_module.f90#L146)). See the [`water_allocation_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_read.f90#L193-L268) reader.

# point_of_diver.wro

After the title line, POD count, and header line, each POD record has five fixed fields followed on the same row by `pous` repeated five-field groups (one per associated POU). The reader reads the first five fields to obtain `ipous`, allocates `pod(ipod)%pou`, backspaces, and rereads the complete line.

## Point-of-diversion count

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [imax](imax.md) | Number of point-of-diversion (POD) records | integer | n/a | — | — |

## POD record (positions 1–5)

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [num](num.md) | POD number stored onto the source object | integer | n/a | — | — |
| [name](name.md) | Name of the POD | string | n/a | — | — |
| [typ](typ.md) | Source object type (`osrc`, `res`, `cha`, `hru`, `aqu`, `can`, `wtow`, `unl`) | string | n/a | — | — |
| [typ_num](typ_num.md) | Source object index within its type array | integer | n/a | — | — |
| [pous](pous.md) | Number of associated places of use (POUs) on this row | integer | n/a | — | — |

## Repeated POU group (positions 6–10, repeated `pous` times)

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [num (POU)](pou_num.md) | Global POU array index (`pou` index) | integer | n/a | — | — |
| [name (POU)](pou_name.md) | Name of the POU | string | n/a | — | — |
| [typ (POU)](pou_typ.md) | POD type label | string | n/a | — | — |
| [typ_num (POU)](pou_typ_num.md) | POD type number | integer | n/a | — | — |
| [right (POU)](pou_right.md) | Water-right identifier | string | n/a | — | — |

{% hint style="warning" %}
SWAT+ main read a third field, `pod_num`, in each POU group. Dev removed it and finds the POD's position in the POU from the POD [num](../place_of_use.wro/pod_num.md) column of `place_of_use.wro` instead ([`water_allocation_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_read.f90#L257-L268)). A main-format file has one extra value per group and is misread on dev.
{% endhint %}

See also [place_of_use.wro](../place_of_use.wro/README.md).

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
