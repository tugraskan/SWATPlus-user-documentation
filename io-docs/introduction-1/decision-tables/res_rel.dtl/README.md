---
description: "This file defines decision tables for reservoir releases."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file defines decision tables for reservoir releases.

# res_rel.dtl

Line 1 is the title. Line 2 starts with the number of decision tables. Leave line 3 blank. For each table, enter a header and the definition row, then a condition header and exactly `conds` condition rows, then an action header and exactly `acts` action rows. Each condition row ends with `alts` comparison entries. Each action row ends with `alts` outcomes in the same order. Leave a blank line after each action block, including the last one. [`dtbl_res_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dtbl_res_read.f90#L39-L73)

Reservoirs and wetlands reference the table by name. The wetland paddy branch uses its separate weir routine. Each day the conditions are evaluated and the releases of all eligible action rows are added together. The reservoir routine then smooths the outflow with the lags in [hydrology.res](../../reservoirs/hydrology.res/README.md). [`res_hydro.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_hydro.f90#L87-L106) · [`res_control.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/res_control.f90#L123-L150)

## Number of decision tables

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [mdtbl](mdtbl.md) | Number of decision tables | integer | n/a | — | — |

## Table definition

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [name](name.md) | Decision table name | string | n/a | — | — |
| [conds](conds.md) | Count of condition entries that follow for this decision table | integer | n/a | — | — |
| [alts](alts.md) | Count of alternatives evaluated for each condition in this decision table | integer | n/a | — | — |
| [acts](acts.md) | Count of actions defined for this decision table | integer | n/a | — | — |

## Conditions

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [var](var.md) | Keyword naming the quantity tested | string | n/a | — | — |
| [ob](ob.md) | Object-type label for the condition | string | n/a | — | — |
| [ob_num](ob_num.md) | Object index or condition-specific number | integer | n/a | — | — |
| [lim_var](lim_var.md) | Named quantity or category for the condition | string | n/a | — | — |
| [lim_op](lim_op.md) | Arithmetic operator for building a threshold where the condition uses one | string | n/a | — | — |
| [lim_const](lim_const.md) | Number used by the condition | real | — | — | — |
| [alt(ic,ial)](alt_ic_ial.md) | Comparison token, repeated once per alternative | string | n/a | — | — |

## Actions

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [typ](typ.md) | Action type, normally release | string | n/a | — | — |
| [ob](ob_2.md) | Object-type label for the action | string | n/a | — | — |
| [ob_num](ob_num_2.md) | Not used in release calculations | integer | n/a | — | — |
| [name](name_2.md) | User label for the action | string | n/a | — | — |
| [option](option.md) | Release equation | string | n/a | — | — |
| [const](const.md) | Primary action value | real | — | — | — |
| [const2](const2.md) | Secondary action value | real | — | — | — |
| [file_pointer](file_pointer.md) | Selector or referenced record name | string | n/a | — | — |
| [act_outcomes(iac,ial)](act_outcomes_iac_ial.md) | Action outcome token, repeated once per alternative | string | n/a | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
