---
description: "This file defines reservoir release conditions and the actions associated with them."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file defines reservoir release conditions and the actions associated with them.

SWAT+ looks for `res_conds.dat` in the simulation working directory; it is not selected through `file.cio`. See the [res_read_conds.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/res_read_conds.f90#L21) reader.

# res_conds.dat

Give the number of release-condition tables, then each table name and its condition/module counts. Follow each table with its condition comparisons and module-specific comparisons. The counts determine the number of entries in each block.

## Table count

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [max_table](max_table.md) | Number of release condition tables to read for reservoirs | integer | n/a | — | — |

## Table definitions

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | Record name | string | n/a | — | — |
| [num_conds](num_conds.md) | Number of condition blocks defined for this table | integer | n/a | — | — |
| [num_modules](num_modules.md) | Number of release modules associated with this table | integer | n/a | — | — |

## Condition comparisons

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [num_conds](num_conds_2.md) | Number of source-variable comparisons in this condition block | integer | n/a | — | — |
| [var](var.md) | Name of the source variable compared in this condition entry | string | n/a | — | — |
| [op](op.md) | Two-character comparison operator applied to the source variable | string | n/a | — | — |
| [val](val.md) | Value compared against the source variable | real | — | — | — |
| [action](action.md) | Numeric action applied when this condition block is satisfied | real | — | — | — |

## Module condition count

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [tnum_conds](tnum_conds.md) | Number of condition entries in each release module | integer | n/a | — | — |

## Module comparisons

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [num_conds](num_conds_3.md) | Number of source-variable comparisons in this module condition entry | integer | n/a | — | — |
| [var](var_2.md) | Name of the source variable compared in this module condition entry | string | n/a | — | — |
| [op](op_2.md) | Two-character comparison operator applied to the module source variable | string | n/a | — | — |
| [val](val_2.md) | Value compared against the module source variable | real | — | — | — |
| [action](action_2.md) | Numeric action applied when this module condition entry is satisfied | real | — | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
