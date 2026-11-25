---
description: "Initial salt-mineral fractions by cell; not used by the model."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This optional file gives the initial fraction of each salt mineral in each cell. It is read only when solute transport is on and `constituents.cs` lists salt ions.

SWAT+ looks for `minerals.gw` in the simulation working directory; it is not selected through `file.cio`. See the [`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1676-L1711) reader.

The fractions are not used: the mineral precipitation–dissolution routine returns without doing anything in this source ([`gwflow_chem.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_chem.f90#L181-L199)). This is listed in `MODEL_ISSUES.md`.

# minerals.gw

The file has a title line, the number of minerals and a heading line. Then, for an unstructured grid, `ncell` lines in cell order, each with one fraction per mineral. For a structured grid, each mineral has a label line, a `read_type` line, and either one value (`single`) or `n_rows` lines of `n_cols` values (`array`) ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1682-L1710)). Structured values are never copied to the cells, and the array they are read into is never allocated.

## Mineral count

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [gw_nminl](gw_nminl.md) | Number of salt minerals | integer | n/a | — | — |

## Unstructured grid

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [fract(m)](fract_m.md) | Fraction of each mineral in the cell | real | fraction | — | 0 to 1 |

## Structured grid

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [read_type](read_type.md) | `single` or `array` | string | n/a | — | — |
| [single_value](single_value.md) | One fraction for all cells | real | fraction | — | — |
| [grid_val(i,j)](grid_val_i_j.md) | Fractions by row and column | real | fraction | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
