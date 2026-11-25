---
description: "This file defines places of use (POUs), their points of diversion (PODs), and their points of return (PORs)."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the tables are based on the SWAT+ Fortran source (dev `aa4179fe`). A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

{% hint style="warning" %}
In [`water_allocation_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_read.f90#L40), the file-open guard is `if (.not. i_exist .or. in_wallo%pou /= "null")`, which enters the open block whenever `in_wallo%pou` is not `"null"` even if the file is missing. In addition, the reader writes positions 2 and 5 of each POR record into the same `num` field, so position 5 is the receiving object number actually used ([`water_allocation_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_read.f90#L104-L105)). On dev, POD records read position 5 into `typ_num` instead.
{% endhint %}

This file defines places of use (POUs), their points of diversion (PODs), and their points of return (PORs). The default filename is `place_of_use.wro`, selected through `in_wallo%pou` in `file.cio` ([`input_file_module.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/input_file_module.f90#L145)). See the [`water_allocation_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_read.f90#L39-L186) reader.

# place_of_use.wro

The file starts with a title line, the POU count, and a header line. Each POU consists of one POU record followed immediately by `pods` POD rows and `pors` POR rows, with no extra header lines between repeated records.

## Place-of-use count

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [imax](imax.md) | Number of place-of-use (POU) records | integer | n/a | — | — |

## Place-of-use record

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [ip](ip.md) | Place-of-use array index (read first as `ipou` to select array slot) | integer | n/a | — | — |
| [name](name.md) | Name of the place of use | string | n/a | — | — |
| [typ](typ.md) | Place-of-use object type (`irr`, `cha`, `res`, `aqu`, `wtp`, `use`, `wtow`, `can`, `orcv`) | string | n/a | — | — |
| [typ_num](typ_num.md) | Object index for the specified POU type | integer | n/a | — | — |
| [pods](pods.md) | Number of point-of-diversion (POD) records for this POU | integer | n/a | — | — |
| [pors](pors.md) | Number of point-of-return (POR) records for this POU | integer | n/a | — | — |
| [dtbl_mx](dtbl_mx.md) | Flow-control decision table name for daily maximum right or duty (`null` if unused) | string | n/a | — | — |
| [rate_max](rate_max.md) | Fixed maximum daily right or duty | real | m^3/s | 0. | — |
| [dtbl_pod_fr](dtbl_pod_fr.md) | Flow-control decision table name for daily POD fractions (`null` if unused) | string | n/a | — | — |
| [dtbl_por_fr](dtbl_por_fr.md) | Flow-control decision table name for daily POR fractions (`null` if unused) | string | n/a | — | — |

## Point-of-diversion (POD) record within a POU

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [pp](pod_pp.md) | Record tag (local variable, not checked) | string | n/a | — | — |
| [num](pod_num.md) | POD number; must match a POD number in `point_of_diver.wro` | integer | n/a | — | — |
| [name](pod_name.md) | Name of the POD | string | n/a | — | — |
| [typ](pod_typ.md) | Type of POD (`cha`, `res`, `aqu`, `can`, etc.) | string | n/a | — | — |
| [typ_num](pod_typ_num.md) | Source object number (read but not used) | integer | n/a | — | — |
| [conv_typ](pod_conv_typ.md) | Conveyance type (`pipe` or `pump`) | string | n/a | — | — |
| [conv_num](pod_conv_num.md) | Conveyance object number | integer | n/a | — | — |
| [dtbl_min](pod_dtbl_min.md) | Decision table name for minimum POD level | string | n/a | — | — |
| [const_min](pod_const_min.md) | Fixed minimum level/threshold for withdrawal | real | varies by POD type | 0. | — |
| [dtbl_wdraw](pod_dtbl_wdraw.md) | Flow-control decision table name for maximum withdrawal (`null` if unused) | string | n/a | — | — |
| [ann_max](pod_ann_max.md) | Maximum withdrawal rate cap | real | m^3/s | 0. | — |
| [frac](pod_frac.md) | Fraction of daily POU duty assigned to this POD | real | fraction | 0. | 0–1 |
| [comp](pod_comp.md) | Compensation flag if POU duty is unmet (`y` / `n`) | string | n/a | — | `y`, `n` |

## Point-of-return (POR) record within a POU

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [pp](por_pp.md) | Record tag (local variable, not checked) | string | n/a | — | — |
| [num (pos 2)](por_num.md) | POR receiving object number (overwritten by position 5) | integer | n/a | — | — |
| [name](por_name.md) | Name of the POR | string | n/a | — | — |
| [typ](por_typ.md) | Receiving object type (`cha`, `res`, `aqu`, `wtp`, `use`, `wtow`, `can`, `orcv`, `hru`) | string | n/a | — | — |
| [num (pos 5)](por_num.md) | POR receiving object number (overwrites position 2) | integer | n/a | — | — |
| [conv_typ](por_conv_typ.md) | Conveyance type (`pipe` or `pump`) | string | n/a | — | — |
| [conv_num](por_conv_num.md) | Conveyance object number | integer | n/a | — | — |
| [dtbl_max](por_dtbl_max.md) | Decision table name for maximum POR level | string | n/a | — | — |
| [const_max](por_const_max.md) | Fixed maximum daily level for return | real | — | 0. | — |
| [ann_max](por_ann_max.md) | Annual maximum inflow | real | m^3/s | 0. | — |
| [frac](por_frac.md) | Fraction of POU outflow routed to this POR | real | fraction | 0. | 0–1 |

See also [point_of_diver.wro](../point_of_diver.wro/README.md).

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
